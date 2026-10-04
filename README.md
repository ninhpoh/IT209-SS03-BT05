# Bài 5: Thiết lập thư mục Web an toàn tại phân vùng hệ thống (/opt/)

## 1. Mục tiêu

- Lưu mã nguồn website tĩnh tại `/opt/my-app/html/`.
- Lưu log Nginx tại `/opt/my-app/logs/`.
- Phân quyền thư mục và tệp tin theo yêu cầu.
- Cấu hình Nginx sử dụng website và log tại `/opt/my-app/`.
- Kiểm tra user `devops` có thể cập nhật website mà không cần `sudo`.

---

## 2. Cấu trúc thư mục

```text
/opt/my-app/
├── html/
│   └── index.html
└── logs/
    ├── access.log
    └── error.log
```

---

## 3. Tạo thư mục Web

```bash
sudo mkdir -p /opt/my-app/html
sudo mkdir -p /opt/my-app/logs
```

Kiểm tra:

```bash
ls -la /opt/my-app/
```

---

## 4. Phân quyền và sở hữu

Gán user và group:

```bash
sudo chown -R devops:www-data /opt/my-app
```

Phân quyền thư mục website:

```bash
sudo chmod 755 /opt/my-app/html
```

Phân quyền file website:

```bash
sudo chmod 644 /opt/my-app/html/index.html
```

Phân quyền thư mục log:

```bash
sudo chmod 775 /opt/my-app/logs
```

Kiểm tra:

```bash
ls -la /opt/my-app/
ls -la /opt/my-app/html/
ls -la /opt/my-app/logs/
```

---

## 5. Cấu hình Nginx

File cấu hình:

```text
/etc/nginx/sites-available/my-app
```

Nội dung:

```nginx
server {
    listen 80;
    listen [::]:80;

    server_name _;

    root /opt/my-app/html;
    index index.html;

    access_log /opt/my-app/logs/access.log;
    error_log /opt/my-app/logs/error.log;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

Tạo symbolic link:

```bash
sudo ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
```

Trong quá trình cấu hình, server `default` của Nginx gây cảnh báo trùng `server_name "_"`, vì vậy đã tắt cấu hình mặc định:

```bash
sudo rm /etc/nginx/sites-enabled/default
```

---

## 6. Kiểm tra cấu hình Nginx

```bash
sudo nginx -t
```

Kết quả:

```text
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```

Reload Nginx:

```bash
sudo systemctl reload nginx
```

Kiểm tra trạng thái:

```bash
sudo systemctl status nginx
```

Kết quả: Nginx ở trạng thái `active (running)`.

---

## 7. Kiểm tra website

```bash
curl http://localhost
```

Kết quả:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My App</title>
</head>
<body>
    <h1>My App - Production Web</h1>
    <p>Website running from /opt/my-app/html/</p>
</body>
</html>
```

Website hoạt động thành công từ thư mục:

```text
/opt/my-app/html/
```

---

## 8. Kiểm tra quyền ghi của user devops

Chuyển sang user `devops`:

```bash
su - devops
```

Cập nhật website không sử dụng `sudo`:

```bash
echo "Update Test" >> /opt/my-app/html/index.html
```

Kiểm tra:

```bash
tail /opt/my-app/html/index.html
```

Kết quả có:

```text
Update Test
```

Điều này chứng minh user `devops` có quyền ghi vào file website mà không cần `sudo`.

---

## 9. Kiểm tra log Nginx

Kiểm tra access log:

```bash
sudo tail /opt/my-app/logs/access.log
```

Kết quả:

```text
127.0.0.1 - - [05/Oct/2026:00:34:38 +0700] "GET / HTTP/1.1" 200 174 "-" "curl/7.81.0"
127.0.0.1 - - [05/Oct/2026:00:36:17 +0700] "GET / HTTP/1.1" 200 186 "-" "curl/7.81.0"
```

Kiểm tra error log:

```bash
sudo tail /opt/my-app/logs/error.log
```

Không có lỗi được ghi nhận.

---

## 10. Kết quả phân quyền cuối cùng

### `/opt/my-app/`

```text
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 logs
```

### `/opt/my-app/html/`

```text
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 devops www-data  186 Oct  5 00:35 index.html
```

### `/opt/my-app/logs/`

Sau khi tạo log bởi Nginx, các file log có thể được tạo bởi tiến trình Nginx với owner `root:root`. Thư mục `logs` vẫn thuộc `devops:www-data` và có quyền `775`, đồng thời Nginx đã ghi log thành công.

```text
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 root   root      439 Oct  5 00:36 access.log
-rw-r--r-- 1 root   root        0 Oct  5 00:28 error.log
```

---

## 11. Kết luận

Bài thực hành đã hoàn thành các nội dung chính:

- Website được đặt tại `/opt/my-app/html/`.
- Log Nginx được đặt tại `/opt/my-app/logs/`.
- Nginx phục vụ website thành công.
- `nginx -t` kiểm tra cấu hình thành công.
- Nginx đang ở trạng thái `active (running)`.
- User `devops` có thể chỉnh sửa `index.html` không cần `sudo`.
- Access log ghi nhận các request HTTP `200`.
- Thư mục `html` và `logs` có owner/group `devops:www-data`.



PC@MSI MINGW64 ~
$ ssh root@160.250.246.216
root@160.250.246.216's password:
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-46-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon Oct  5 12:25:59 AM +07 2026

  System load:  0.0                Processes:             99
  Usage of /:   21.4% of 19.59GB   Users logged in:       0
  Memory usage: 23%                IPv4 address for eth0: 160.250.246.216
  Swap usage:   0%

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

357 updates can be applied immediately.
253 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

New release '24.04.5 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Sun Oct  4 19:27:13 2026 from 14.231.89.17
root@azvps-tm7x9chmo:~# id devops
uid=1000(devops) gid=1000(devops) groups=1000(devops)
root@azvps-tm7x9chmo:~# sudo mkdir -p /opt/my-app/html
sudo mkdir -p /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 root root 4096 Oct  5 00:26 .
drwxr-xr-x 3 root root 4096 Oct  5 00:26 ..
drwxr-xr-x 2 root root 4096 Oct  5 00:26 html
drwxr-xr-x 2 root root 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo nano /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chown -R devops:www-data /opt/my-app
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo chmod 755 /opt/my-app/html
root@azvps-tm7x9chmo:~# sudo chmod 644 /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chmod 775 /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -ld /opt/my-app/logs
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:26 /opt/my-app/logs
root@azvps-tm7x9chmo:~# sudo nano /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: [warn] conflicting server name "_" on 0.0.0.0:80, ignored
nginx: [warn] conflicting server name "_" on [::]:80, ignored
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# ^C
root@azvps-tm7x9chmo:~#
PC@MSI MINGW64 ~
$ ssh root@160.250.246.216
root@160.250.246.216's password:
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-46-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon Oct  5 12:25:59 AM +07 2026

  System load:  0.0                Processes:             99
  Usage of /:   21.4% of 19.59GB   Users logged in:       0
  Memory usage: 23%                IPv4 address for eth0: 160.250.246.216
  Swap usage:   0%

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

357 updates can be applied immediately.
253 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

New release '24.04.5 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Sun Oct  4 19:27:13 2026 from 14.231.89.17
root@azvps-tm7x9chmo:~# id devops
uid=1000(devops) gid=1000(devops) groups=1000(devops)
root@azvps-tm7x9chmo:~# sudo mkdir -p /opt/my-app/html
sudo mkdir -p /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 root root 4096 Oct  5 00:26 .
drwxr-xr-x 3 root root 4096 Oct  5 00:26 ..
drwxr-xr-x 2 root root 4096 Oct  5 00:26 html
drwxr-xr-x 2 root root 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo nano /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chown -R devops:www-data /opt/my-app
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo chmod 755 /opt/my-app/html
root@azvps-tm7x9chmo:~# sudo chmod 644 /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chmod 775 /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -ld /opt/my-app/logs
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:26 /opt/my-app/logs
root@azvps-tm7x9chmo:~# sudo nano /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: [warn] conflicting server name "_" on 0.0.0.0:80, ignored
nginx: [warn] conflicting server name "_" on [::]:80, ignored
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# ^C
root@azvps-tm7x9chmo:~#ls -la /etc/nginx/sites-enabled/
PC@MSI: command not found
$: command not found
>
>
>
>
> ádas
> sdf
>
.bash_history    .cache/          .lesshst         .profile         recipe_-1.log    recipe_-799.log  .ssh/
.bashrc          exec_recipe.log  .local/          recipe_-16.log   recipe_-213.log  snap/            .viminfo
>
> sfadss
> fsdfs
> dsf
> ^C
root@azvps-tm7x9chmo:~# ls -la /etc/nginx/sites-enabled/
total 8
drwxr-xr-x 2 root root 4096 Oct  5 00:28 .
drwxr-xr-x 8 root root 4096 Oct  1 22:31 ..
lrwxrwxrwx 1 root root   34 Oct  1 22:31 default -> /etc/nginx/sites-available/default
lrwxrwxrwx 1 root root   42 Oct  4 19:29 multi-port.conf -> /etc/nginx/sites-available/multi-port.conf
lrwxrwxrwx 1 root root   33 Oct  5 00:28 my-app -> /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo rm /etc/nginx/sites-enabled/default
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# sudo systemctl reload nginx
root@azvps-tm7x9chmo:~# sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Sun 2026-10-04 19:33:16 +07; 5h 0min ago
       Docs: man:nginx(8)
    Process: 17881 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 17883 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 20798 ExecReload=/usr/sbin/nginx -g daemon on; master_process on; -s reload (code=exited, status=0/SUCCESS)
   Main PID: 17884 (nginx)
      Tasks: 2 (limit: 1029)
     Memory: 3.5M
        CPU: 135ms
     CGroup: /system.slice/nginx.service
             ├─17884 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             └─20799 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: nginx.service: Deactivated successfully.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Stopped A high performance web server and a reverse proxy server.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Starting A high performance web server and a reverse proxy server...
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Started A high performance web server and a reverse proxy server.
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloading A high performance web server and a reverse proxy server...
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloaded A high performance web server and a reverse proxy server.
root@azvps-tm7x9chmo:~# sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Sun 2026-10-04 19:33:16 +07; 5h 0min ago
       Docs: man:nginx(8)
    Process: 17881 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 17883 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 20798 ExecReload=/usr/sbin/nginx -g daemon on; master_process on; -s reload (code=exited, status=0/SUCCESS)
   Main PID: 17884 (nginx)
      Tasks: 2 (limit: 1029)
     Memory: 3.5M
        CPU: 135ms
     CGroup: /system.slice/nginx.service
             ├─17884 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             └─20799 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: nginx.service: Deactivated successfully.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Stopped A high performance web server and a reverse proxy server.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Starting A high performance web server and a reverse proxy server...
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Started A high performance web server and a reverse proxy server.
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloading A high performance web server and a reverse proxy server...
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloaded A high performance web server and a reverse proxy server.
root@azvps-tm7x9chmo:~# curl http://localhost
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
root@azvps-tm7x9chmo:~# su - devops
devops@azvps-tm7x9chmo:~$ echo "Update Test" >> /opt/my-app/html/index.html
devops@azvps-tm7x9chmo:~$ tail /opt/my-app/html/index.html
<html>
<head>
    <title>My App</title>
</head>
<body>
    <h1>My App - Production Web</h1>
    <p>Website running from /opt/my-app/html/</p>
</body>
</html>
Update Test
devops@azvps-tm7x9chmo:~$ exit
logout
root@azvps-tm7x9chmo:~# curl http://localhost
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
Update Test
root@azvps-tm7x9chmo:~# sudo tail /opt/my-app/logs/access.log
127.0.0.1 - - [05/Oct/2026:00:34:38 +0700] "GET / HTTP/1.1" 200 174 "-" "curl/7.81.0"
127.0.0.1 - - [05/Oct/2026:00:36:17 +0700] "GET / HTTP/1.1" 200 186 "-" "curl/7.81.0"
root@azvps-tm7x9chmo:~# sudo tail /opt/my-app/logs/error.log
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/html/
total 12
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 devops www-data  186 Oct  5 00:35 index.html
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/logs/
total 12
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 root   root      439 Oct  5 00:36 access.log
-rw-r--r-- 1 root   root        0 Oct  5 00:28 error.log
root@azvps-tm7x9chmo:~#

PC@MSI MINGW64 ~
$ ssh root@160.250.246.216
root@160.250.246.216's password:
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-46-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon Oct  5 12:25:59 AM +07 2026

  System load:  0.0                Processes:             99
  Usage of /:   21.4% of 19.59GB   Users logged in:       0
  Memory usage: 23%                IPv4 address for eth0: 160.250.246.216
  Swap usage:   0%

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

357 updates can be applied immediately.
253 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

New release '24.04.5 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Sun Oct  4 19:27:13 2026 from 14.231.89.17
root@azvps-tm7x9chmo:~# id devops
uid=1000(devops) gid=1000(devops) groups=1000(devops)
root@azvps-tm7x9chmo:~# sudo mkdir -p /opt/my-app/html
sudo mkdir -p /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 root root 4096 Oct  5 00:26 .
drwxr-xr-x 3 root root 4096 Oct  5 00:26 ..
drwxr-xr-x 2 root root 4096 Oct  5 00:26 html
drwxr-xr-x 2 root root 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo nano /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chown -R devops:www-data /opt/my-app
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo chmod 755 /opt/my-app/html
root@azvps-tm7x9chmo:~# sudo chmod 644 /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chmod 775 /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -ld /opt/my-app/logs
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:26 /opt/my-app/logs
root@azvps-tm7x9chmo:~# sudo nano /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: [warn] conflicting server name "_" on 0.0.0.0:80, ignored
nginx: [warn] conflicting server name "_" on [::]:80, ignored
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# ^C
root@azvps-tm7x9chmo:~#
PC@MSI MINGW64 ~
$ ssh root@160.250.246.216
root@160.250.246.216's password:
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-46-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon Oct  5 12:25:59 AM +07 2026

  System load:  0.0                Processes:             99
  Usage of /:   21.4% of 19.59GB   Users logged in:       0
  Memory usage: 23%                IPv4 address for eth0: 160.250.246.216
  Swap usage:   0%

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

357 updates can be applied immediately.
253 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

New release '24.04.5 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Sun Oct  4 19:27:13 2026 from 14.231.89.17
root@azvps-tm7x9chmo:~# id devops
uid=1000(devops) gid=1000(devops) groups=1000(devops)
root@azvps-tm7x9chmo:~# sudo mkdir -p /opt/my-app/html
sudo mkdir -p /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 root root 4096 Oct  5 00:26 .
drwxr-xr-x 3 root root 4096 Oct  5 00:26 ..
drwxr-xr-x 2 root root 4096 Oct  5 00:26 html
drwxr-xr-x 2 root root 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo nano /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chown -R devops:www-data /opt/my-app
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:26 logs
root@azvps-tm7x9chmo:~# sudo chmod 755 /opt/my-app/html
root@azvps-tm7x9chmo:~# sudo chmod 644 /opt/my-app/html/index.html
root@azvps-tm7x9chmo:~# sudo chmod 775 /opt/my-app/logs
root@azvps-tm7x9chmo:~# ls -ld /opt/my-app/logs
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:26 /opt/my-app/logs
root@azvps-tm7x9chmo:~# sudo nano /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: [warn] conflicting server name "_" on 0.0.0.0:80, ignored
nginx: [warn] conflicting server name "_" on [::]:80, ignored
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# ^C
root@azvps-tm7x9chmo:~#ls -la /etc/nginx/sites-enabled/
PC@MSI: command not found
$: command not found
>
>
>
>
> ádas
> sdf
>
.bash_history    .cache/          .lesshst         .profile         recipe_-1.log    recipe_-799.log  .ssh/
.bashrc          exec_recipe.log  .local/          recipe_-16.log   recipe_-213.log  snap/            .viminfo
>
> sfadss
> fsdfs
> dsf
> ^C
root@azvps-tm7x9chmo:~# ls -la /etc/nginx/sites-enabled/
total 8
drwxr-xr-x 2 root root 4096 Oct  5 00:28 .
drwxr-xr-x 8 root root 4096 Oct  1 22:31 ..
lrwxrwxrwx 1 root root   34 Oct  1 22:31 default -> /etc/nginx/sites-available/default
lrwxrwxrwx 1 root root   42 Oct  4 19:29 multi-port.conf -> /etc/nginx/sites-available/multi-port.conf
lrwxrwxrwx 1 root root   33 Oct  5 00:28 my-app -> /etc/nginx/sites-available/my-app
root@azvps-tm7x9chmo:~# sudo rm /etc/nginx/sites-enabled/default
root@azvps-tm7x9chmo:~# sudo nginx -t
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
root@azvps-tm7x9chmo:~# sudo systemctl reload nginx
root@azvps-tm7x9chmo:~# sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Sun 2026-10-04 19:33:16 +07; 5h 0min ago
       Docs: man:nginx(8)
    Process: 17881 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 17883 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 20798 ExecReload=/usr/sbin/nginx -g daemon on; master_process on; -s reload (code=exited, status=0/SUCCESS)
   Main PID: 17884 (nginx)
      Tasks: 2 (limit: 1029)
     Memory: 3.5M
        CPU: 135ms
     CGroup: /system.slice/nginx.service
             ├─17884 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             └─20799 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: nginx.service: Deactivated successfully.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Stopped A high performance web server and a reverse proxy server.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Starting A high performance web server and a reverse proxy server...
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Started A high performance web server and a reverse proxy server.
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloading A high performance web server and a reverse proxy server...
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloaded A high performance web server and a reverse proxy server.
root@azvps-tm7x9chmo:~# sudo systemctl status nginx
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Sun 2026-10-04 19:33:16 +07; 5h 0min ago
       Docs: man:nginx(8)
    Process: 17881 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 17883 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)
    Process: 20798 ExecReload=/usr/sbin/nginx -g daemon on; master_process on; -s reload (code=exited, status=0/SUCCESS)
   Main PID: 17884 (nginx)
      Tasks: 2 (limit: 1029)
     Memory: 3.5M
        CPU: 135ms
     CGroup: /system.slice/nginx.service
             ├─17884 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
             └─20799 "nginx: worker process" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: nginx.service: Deactivated successfully.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Stopped A high performance web server and a reverse proxy server.
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Starting A high performance web server and a reverse proxy server...
Oct 04 19:33:16 azvps-tm7x9chmo systemd[1]: Started A high performance web server and a reverse proxy server.
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloading A high performance web server and a reverse proxy server...
Oct 05 00:33:33 azvps-tm7x9chmo systemd[1]: Reloaded A high performance web server and a reverse proxy server.
root@azvps-tm7x9chmo:~# curl http://localhost
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
root@azvps-tm7x9chmo:~# su - devops
devops@azvps-tm7x9chmo:~$ echo "Update Test" >> /opt/my-app/html/index.html
devops@azvps-tm7x9chmo:~$ tail /opt/my-app/html/index.html
<html>
<head>
    <title>My App</title>
</head>
<body>
    <h1>My App - Production Web</h1>
    <p>Website running from /opt/my-app/html/</p>
</body>
</html>
Update Test
devops@azvps-tm7x9chmo:~$ exit
logout
root@azvps-tm7x9chmo:~# curl http://localhost
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
Update Test
root@azvps-tm7x9chmo:~# sudo tail /opt/my-app/logs/access.log
127.0.0.1 - - [05/Oct/2026:00:34:38 +0700] "GET / HTTP/1.1" 200 174 "-" "curl/7.81.0"
127.0.0.1 - - [05/Oct/2026:00:36:17 +0700] "GET / HTTP/1.1" 200 186 "-" "curl/7.81.0"
root@azvps-tm7x9chmo:~# sudo tail /opt/my-app/logs/error.log
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/
total 16
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 .
drwxr-xr-x 3 root   root     4096 Oct  5 00:26 ..
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 html
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 logs
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/html/
total 12
drwxr-xr-x 2 devops www-data 4096 Oct  5 00:27 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 devops www-data  186 Oct  5 00:35 index.html
root@azvps-tm7x9chmo:~# ls -la /opt/my-app/logs/
total 12
drwxrwxr-x 2 devops www-data 4096 Oct  5 00:28 .
drwxr-xr-x 4 devops www-data 4096 Oct  5 00:26 ..
-rw-r--r-- 1 root   root      439 Oct  5 00:36 access.log
-rw-r--r-- 1 root   root        0 Oct  5 00:28 error.log
root@azvps-tm7x9chmo:~#

---
date: "2022-11-24T21:04:00+00:00"
title: "How to Setup MariaDB Database Server on AlmaLinux 8"
---

### a) Installing _The MariaBD Server_

Install the _MariaDB Server_.  
`sudo dnf module install mariadb`

### b) Enabling Autostart

To tell _systemd_ to start _mariadb_ **service** automatically at boot, enable it.  
`sudo systemctl enable mariadb.service`

### c) Starting

Start the _mariadb_.  
`sudo systemctl start mariadb.service`  
The database server will start listening on port **3306** by default.

### d) Securing

You should improve the security of your _MariaDB_ installation. So, run the command below and follow the upcoming instructions.  
`sudo mysql_secure_installation`  

**It will ask you to:**

- change password of _root_ account,
- remove anonymous users,
- disallow remote login of the _root_ account,
- remove test database and access to it,
- reload privilege tables now, and more.

### e) Usage

You can use the official command-line client _mysql_.  
<https://mariadb.com/kb/en/mysql-command-line-client/>

Additionally, you can use _mysqlcheck_, a command-line interface to the _CHECK TABLE_, _REPAIR TABLE_, _ANALYZE TABLE_ and _OPTIMIZE TABLE_ commands.  
<https://mariadb.com/kb/en/mysqlcheck/>

Find some officially supported graphical and enhanced clients here:  
<https://mariadb.com/kb/en/graphical-and-enhanced-clients/>

---

**Next:** <https://bitscoper.dev/posts/how-to-enable-remote-access-to-mariadb-database-server-on-almalinux-8/>

---

### Documentations

- <https://mariadb.com/resources/blog/how-to-install-mariadb-on-rhel8-centos8/>
- <https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/deploying_different_types_of_servers/using-databases>
- <https://mariadb.com/kb/en/mysql_secure_installation/>

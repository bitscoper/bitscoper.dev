---
date: "2022-12-03T21:06:00+00:00"
title: "How to Setup WebDAV Server on Oracle Linux 8"
---

**_WebDAV (Web Distributed Authoring and Versioning)_** is a part of _Apache HTTP Server_ software.

### a) Installing The _Apache HTTP Server_

Install the _Apache HTTP Server_.  
`sudo dnf module install httpd`

### b) Enabling Autostart

To tell _systemd_ to start _httpd_ **service** automatically at boot, enable it.  
`sudo systemctl enable httpd.service`

### c) Disabling Default Web Page

(This step is optional.)  
`sudo sed -i 's/^/#&/g' /etc/httpd/conf.d/welcome.conf`

### d) Disabling Default File Listing

(This step is optional.)  
`sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/httpd/conf/httpd.conf`

### e) Making Directory

Create a directory named **webdav** from which you want to serve.  
`sudo mkdir /var/www/html/webdav`

### f) Transferring Ownership

Transfer the ownership of the _webdav_ directory and its subdirectories and contents to **_apache_** user recursively.  
`sudo chown -R apache:apache /var/www/html/webdav`

### g) Assigning Permissions

Assign read and execute access for all users and also write access for the owner (_apache_) of the _webdav_ directory and its subdirectories and contents recursively.  
`sudo chmod -R 755 /var/www/html/webdav`

### h) Creating A _WebDAV_ User

Create an _WebDAV_ user and assign a password to it.  
`sudo htpasswd -c /etc/httpd/.htpasswd test_user`

### i) Creating Virtual Host

Edit or create the **/etc/httpd/conf.d/webdav.conf** file on your favorite text editor with superuser privileges and populate the file with the configuration below.

```apache
Alias /webdav /var/www/html/webdav

DAV On
AuthType Basic
AuthName "WebDav Authorization Required"
AuthUserFile /etc/httpd/.htpasswd
Require valid-user
```

### j) Starting

Start the _httpd_ **service**.  
`sudo systemctl start httpd.service`  
The web server will load _WebDAV_ modules and start listening on port **80** by default.

### k) Letting _FirewallD_ to Know

You may have to add the port to the _FirewallD_‘s allow list. Adding the _http_ service would do so.  
`sudo firewall-cmd --zone=public --permanent --add-service=http`  
Then reload the _FirewallD_.  
`sudo firewall-cmd --reload`

---

### Documentation

- <https://httpd.apache.org/docs/2.4/mod/mod_dav.html>

---
date: "2022-07-20T20:38:00+00:00"
title: "How to Enable Gzip Compression With Apache HTTP Server on AlmaLinux 8"
---

## a) Configuring

Edit the **/etc/httpd/conf/httpd.conf** file in your preferred text editor with superuser privileges.

First, instruct the server to load the _mod_deflate_ module by adding the following line:

```apache
LoadModule deflate_module modules/mod_deflate.so
```

Next, add the MIME (Multipurpose Internet Mail Extensions) types that you want the server to compress:

```apache
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE application/javascript
    AddOutputFilterByType DEFLATE application/rss+xml
    AddOutputFilterByType DEFLATE application/vnd.ms-fontobject
    AddOutputFilterByType DEFLATE application/x-font
    AddOutputFilterByType DEFLATE application/x-font-opentype
    AddOutputFilterByType DEFLATE application/x-font-otf
    AddOutputFilterByType DEFLATE application/x-font-truetype
    AddOutputFilterByType DEFLATE application/x-font-ttf
    AddOutputFilterByType DEFLATE application/x-javascript
    AddOutputFilterByType DEFLATE application/xhtml+xml
    AddOutputFilterByType DEFLATE application/xml
    AddOutputFilterByType DEFLATE font/opentype
    AddOutputFilterByType DEFLATE font/otf
    AddOutputFilterByType DEFLATE font/ttf
    AddOutputFilterByType DEFLATE image/svg+xml
    AddOutputFilterByType DEFLATE image/x-icon
    AddOutputFilterByType DEFLATE text/css
    AddOutputFilterByType DEFLATE text/html
    AddOutputFilterByType DEFLATE text/javascript
    AddOutputFilterByType DEFLATE text/plain
    AddOutputFilterByType DEFLATE text/xml
</IfModule>
```

## b) Restarting

Restart the _httpd_ **service** to apply the changes:

```sh
sudo systemctl restart httpd.service
```

---

## Documentation

- <https://httpd.apache.org/docs/2.4/mod/mod_deflate.html>

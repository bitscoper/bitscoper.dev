---
date: "2022-10-09T20:55:00+00:00"
title: "How to Setup a Reverse Proxy With Apache HTTP Server on AlmaLinux 8"
---

Let’s assume we want to make the **example.com** server sit in front of the **localhost:8080** server.

### a) Creating Virtual Host

Open the **/etc/httpd/conf.d/sites.conf** file with superuser privileges and add the following lines.

```apache
<VirtualHost *:80>
    ServerName example.com

    ProxyPreserveHost On
    ProxyPass / http://localhost:8080/
    ProxyPassReverse / http://localhost:8080/
</VirtualHost>
```

### b) Restarting

Restart the _httpd_ **service**.  
`sudo systemctl restart httpd.service`

---

### Documentations

- <https://httpd.apache.org/docs/2.4/mod/mod_proxy.html>
- <https://httpd.apache.org/docs/2.4/howto/reverse_proxy.html>

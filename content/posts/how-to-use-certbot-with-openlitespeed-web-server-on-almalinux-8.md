---
date: "2023-01-06T21:12:00+00:00"
title: "How to Use Certbot With OpenLiteSpeed Web Server on AlmaLinux 8"
---

### a) Installing The _Certbot_

The _Certbot_ is available on _EPEL (Extra Packages for Enterprise Linux)_ repository. So, install the repository first.  
`sudo dnf install epel-release`  
Then install the _Certbot_.  
`sudo dnf install certbot`

### b) Creating Certificate Using The _Certbot_

Here, we want to create the certificate for **_yourdomain.com_** domain which is being served from the **_/public-path-of-website/_** directory and the certificate’s RSA key size will be **_4096_** bits.  
`sudo certbot certonly --webroot -w /public-path-of-website/ -d yourdomain.com --rsa-key-size=4096`  

Before this, you must ensure the availability of the website through HTTP. After finishing, the _Certbot_ will show you the path of the generated **Private Key File** and **Certificate File**. Note these down, you need to let the _OpenLiteSpeed Web Server_ know these locations.

### c) Configuring The _OpenLiteSpeed Web Server_

Go to your _OpenLiteSpeed Web Server_‘s _WebAdmin Console_ and log in. Navigate to **_Virtual Hosts_** and then click on **_View_** icon related to your desired virtual host. Then navigate to **_SSL > SSL Private Key & Certificate_** and click on its related **_Edit_** icon.  

Set the path of the **Private Key File** and the **Certificate File** and set the **_Chained Certificate_** option to **_Yes_**. Then click on **_Save_** icon.

### d) Restarting

Changes will take effect after you give the _OpenLiteSpeed Web Server_ a graceful restart. (Graceful restart ensures zero downtime.)

- **In case of its _WebAdmin Console_:** You can just click on **_Graceful Restart_** icon and then proceed to **_Yes_**.
- **In case of _systemd_:** `sudo systemctl restart openlitespeed.service` or `sudo systemctl restart lsws.service`

---

### Documentations

- <https://eff-certbot.readthedocs.io/en/stable/>
- <https://certbot.eff.org/instructions?ws=other&os=centosrhel8>

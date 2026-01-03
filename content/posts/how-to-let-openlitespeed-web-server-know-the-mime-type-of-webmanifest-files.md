---
date: "2022-09-08T20:49:00+00:00"
title: "How to Let OpenLiteSpeed Web Server Know the MIME Type of WebManifest Files"
---

By default, the _OpenLiteSpeed Web Server_ does not know the MIME type (**application/json**) of the **.webmanifest** manifest files of Progressive Web Applications (PWA), so the mentioned files are served with the **application/octet-stream** MIME type that actually represents unknown binary files.

### a) Configuring

Open the **/usr/local/lsws/conf/mime.properties** file on your favorite text editor with superuser privileges and add the following line mentioning the specific MIME type of your desired file.  
`webmanifest = application/json`

### b) Restarting

Changes will take effect after you give the _OpenLiteSpeed Web Server_ a graceful restart. (Graceful restart ensures zero downtime.)

- **In case of its _WebAdmin Console_:** Just click on **_Graceful Restart_** icon and then proceed to **_Yes_**.
- **In case of _systemd_:** `sudo systemctl restart openlitespeed.service` or `sudo systemctl restart lsws.service`

---

### Documentation

- <https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:config:add-mime-type>

---
date: "2024-04-07T19:50:26+00:00"
title: "How to Change systemd-boot Timeout on Arch Linux"
---

Open the **/boot/loader/loader.conf** file in your preferred text editor with superuser privileges and edit the following value:

```conf
timeout 2
```

In this example, the timeout value is changed from **3** to **2**.

Reboot your lovely system and enjoy!

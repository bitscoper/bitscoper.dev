---
date: "2024-04-07T19:57:14+00:00"
title: "How to Set the Highest Resolution for systemd-boot on Arch Linux"
---

Open the **/boot/loader/loader.conf** file on your favorite text editor with superuser privileges and edit the following value.  
Uncomment it if needed and set the value to _max_.

`console-mode max`

Just reboot your lovely system and enjoy!

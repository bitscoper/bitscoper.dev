---
date: "2023-11-11T19:35:19+00:00"
title: "How to Setup memcached on AlmaLinux 8"
---

### a) Installing

Install the required packages first.  
`sudo dnf install memcached libmemcached`

### b) Enabling Autostart

To tell _systemd_ to start _memcached_ service automatically at boot, enable it.  
`sudo systemctl enable memcached.service`

### c) Starting

Start the _memcached_ service.  
`sudo systemctl start memcached.service`  
By default, the _memcached_ listens on port **11211**.

### d) Letting _FirewallD_ to Know

You may have to add the port to the _FirewallD_‘s allow list, if you need to access it beyond localhost.  
`sudo firewall-cmd --zone=public --permanent --add-port=11211/tcp`  
Then reload the _FirewallD_.  
`sudo firewall-cmd --reload`

---

### Resources

- <https://memcached.org/>
- <https://memcached.org/about>

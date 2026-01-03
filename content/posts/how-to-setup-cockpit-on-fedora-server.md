---
date: "2022-10-19T20:58:00+00:00"
title: "How to Setup Cockpit on Fedora Server"
---

The _Cockpit_ is a robust and feature-rich web-based Graphical User Interface (GUI) software that is purpose-built for managing and monitoring servers. Developed as an open-source software, it offers system administrators a user-friendly way to perform essential system tasks, including configuring networking settings, managing storage, monitoring system logs, and more.

### a) Installing The Cockpit

Install the _Cockpit_.  
`sudo dnf install cockpit`  

**Optional:** you can find its add-ons by searching.  
`sudo dnf search cockpit`

### b) Enabling Autostart

To tell _systemd_ to start the _cockpit_ **socket** automatically at boot, you have to enable it.  
`sudo systemctl enable cockpit.socket`

### c) Starting

Start the _cockpit_ **socket** now.  
`sudo systemctl start cockpit.socket`  

The _Cockpit_ server will start listening on port **9090** by default.

### d) Letting _FirewallD_ to Know

You may have to add the _cockpit_ service to the _FirewallD_‘s allow list if you want to access it from another device.  
`sudo firewall-cmd --add-service=cockpit --permanent`  

Then reload the _FirewallD_.  
`sudo firewall-cmd --reload`

### e) Login

Browse <https://localhost:9090/> or <https://your_ip_address:9090/> from any (local) web browser and login with your user credentials.

---

### Documentations

- <https://cockpit-project.org/running.html#fedora>
- <https://cockpit-project.org/guide/latest/>

---

**See also:** <https://bitscoper.dev/posts/how-to-solve-cockpit-ostree-unavailability-error-on-fedora-server/>

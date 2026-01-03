---
date: "2022-10-29T21:00:00+00:00"
title: "How to Setup dnf-automatic"
---

### a) Installing The _dnf-automatic_

Install the _dnf-automatic_.

```sh
sudo dnf install dnf-automatic
```

### b) Configuring

Edit the **/etc/dnf/automatic.conf** file with superuser privileges.  
To enable automatic installation of all available updates, modify the **[commands]** section as follows:

```conf
apply_updates=yes
download_updates=yes
network_online_timeout=60
random_sleep=0
upgrade_type=default
```

The configuration supports many other options. Refer to the official documentation to tailor _dnf-automatic_ to your needs.

### c) Enabling Autostart

Enable the _dnf-automatic_ **timer** to start automatically at boot.

```sh
sudo systemctl enable dnf-automatic.timer
```

### d) Starting

Start the _dnf-automatic_ **timer**.

```sh
sudo systemctl start dnf-automatic.timer
```

### Documentation

- <https://dnf.readthedocs.io/en/latest/automatic.html>

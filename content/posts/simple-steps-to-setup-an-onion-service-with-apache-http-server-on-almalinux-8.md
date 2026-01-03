---
date: "2023-01-26T21:16:00+00:00"
title: "Simple Steps to Setup an Onion Service With Apache HTTP Server on AlmaLinux 8"
---

## 1) Setting Up the _Apache HTTP Server_

### a) Installing

Install the _Apache HTTP Server_ module:

```sh
sudo dnf module install httpd
```

### b) Enabling Autostart

To tell _systemd_ to start the _httpd_ **service** automatically at boot, enable it:

```sh
sudo systemctl enable httpd.service
```

### c) Starting

Start the _httpd_ **service**:

```sh
sudo systemctl start httpd.service
```

The web server will start listening on port **80** by default, which will be your **HiddenServicePort**.

### d) Letting _FirewallD_ Know

You may need to add the port to _FirewallD_’s allow list. Adding the **http** service will do so:

```sh
sudo firewall-cmd --zone=public --permanent --add-service=http
```

Then reload _FirewallD_:

```sh
sudo firewall-cmd --reload
```

## 2) Setting Up _Tor_

### a) Installing

Install _Tor_:

```sh
sudo dnf install tor
```

### b) Configuring

Open the `/etc/tor/torrc` file in your preferred text editor with superuser privileges and add or edit the following lines:

```text
HiddenServiceDir /var/lib/tor/our_hidden_project

HiddenServicePort 80 127.0.0.1:80
```

### c) Enabling Autostart

To tell _systemd_ to start the _tor_ **service** automatically at boot, enable it:

```sh
sudo systemctl enable tor.service
```

### d) Starting

Start the _tor_ **service**:

```sh
sudo systemctl start tor.service
```

The specified **HiddenServiceDir** directory will be created automatically. Inside this directory, you will find a file named **hostname**, which contains your onion service address.

---

## Documentation

- <https://httpd.apache.org/docs/2.4/>
- <https://community.torproject.org/onion-services/setup/>

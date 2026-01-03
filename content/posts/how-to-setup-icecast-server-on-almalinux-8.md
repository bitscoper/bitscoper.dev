---
date: "2022-11-04T21:01:00+00:00"
title: "How to Setup Icecast Server on AlmaLinux 8"
---

### a) Installing Tools & Dependencies

Install the _Development Tools_ group.

```sh
sudo dnf groupinstall "Development Tools"
```

Then install the following dependencies:

- _curl-devel_
- _libtheora-devel_
- _libvorbis-devel_
- _libxslt-devel_
- _speex-devel_
- _libshout_

```sh
sudo dnf install curl-devel libtheora-devel libvorbis-devel libxslt-devel speex-devel libshout
```

### b) Building & Installing Icecast

Download the archive file of the Icecast source code. Prefer the latest version if available.

```sh
wget http://downloads.xiph.org/releases/icecast/icecast-2.4.4.tar.gz
```

Then extract the archive file and enter the extracted directory.

```sh
tar -zxvf icecast-2.4.4.tar.gz
cd icecast-2.4.4
```

Prepare the environment for building.

```sh
./configure --sysconfdir=/etc --localstatedir=/var
```

Build and install.

```sh
make
sudo make install
```

### c) Creating User

Create a user named **icecast**.

```sh
sudo useradd -s /sbin/nologin icecast
```

### d) Making Directories

Create the following directories:

- **/var/run/icecast**
- **/var/log/icecast**

```sh
sudo mkdir -p /var/run/icecast
sudo mkdir -p /var/log/icecast
```

### e) Transferring Ownership

Transfer ownership of the created directories and their contents to the _icecast_ user recursively.

```sh
sudo chown -R icecast:icecast /var/run/icecast
sudo chown -R icecast:icecast /var/log/icecast
```

### f) Replacing Log Directory

Inside the **/etc/icecast.xml** file, replace the log directory path.

```sh
sudo sed -i -e "s,/usr/local/var/log/icecast,/var/log/icecast,g" /etc/icecast.xml
```

### g) Putting _systemd_ Unit File

Create a _systemd_ unit file for Icecast.

```sh
sudo tee /etc/systemd/system/icecast.service > /dev/null <<'EOF'
[Unit]
Description=Icecast
After=network.target

[Service]
Type=simple
Restart=always
RestartSec=5
User=icecast
ExecStart=/usr/local/bin/icecast -c /etc/icecast.xml
ExecReload=/usr/bin/kill -HUP $MAINPID

[Install]
WantedBy=multi-user.target
EOF
```

### h) Reloading _systemd_ Manager Configuration

Reload the _systemd_ manager configuration.

```sh
sudo systemctl daemon-reload
```

### i) Configuring the Icecast Server

Edit **/etc/icecast.xml** and set the port.

```xml
<port>17101</port>
```

Also change **admin-user**, **admin-password**, **source-password**, and other settings as needed.

### j) Enabling Autostart

Enable the Icecast service at boot.

```sh
sudo systemctl enable icecast.service
```

### k) Starting

Start the Icecast service.

```sh
sudo systemctl start icecast.service
```

The server will listen on port **17101**.

### l) Making _FirewallD_ to Allow

Allow the port in FirewallD and reload.

```sh
sudo firewall-cmd --zone=public --permanent --add-port=17101/tcp
sudo firewall-cmd --reload
```

### Documentation

- <https://icecast.org/docs/>

---
date: "2022-06-14T20:23:00+00:00"
title: "How to Change Port of SSH Server on AlmaLinux 8"
---

## a) Configuring the _OpenSSH_ Server

You can specify any port **from 1024 to 65535**. In this example, port **26170** is used instead of the default SSH port **22**.

Edit the **/etc/ssh/sshd_config** file in your preferred text editor with superuser privileges and add or modify the following line:

```conf
Port 26170
```

## b) Adding the Port to _SELinux_ Policy Configuration

Add the new port to the SELinux (Security-Enhanced Linux) policy configuration:

```sh
sudo semanage port -a -t ssh_port_t -p tcp 26170
```

## c) Letting _FirewallD_ Know

Remove the default SSH port from the _firewalld_ allow list. Removing the **ssh** service will do so:

```sh
sudo firewall-cmd --permanent --remove-service=ssh
```

Add the new SSH port to the allow list:

```sh
sudo firewall-cmd --permanent --add-port=26170/tcp
```

Then reload _firewalld_:

```sh
sudo firewall-cmd --reload
```

## d) Restarting the _OpenSSH_ Server

Restart the _sshd_ **service** to apply the changes:

```sh
sudo systemctl restart sshd.service
```

This will perform a graceful restart of the SSH server.

---

## Documentation

- <https://firewalld.org/documentation/howto/open-a-port-or-service.html>

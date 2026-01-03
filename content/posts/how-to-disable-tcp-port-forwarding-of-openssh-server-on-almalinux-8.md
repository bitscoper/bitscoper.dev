---
date: "2022-06-28T20:27:00+00:00"
title: "How to Disable TCP Port Forwarding of OpenSSH Server on AlmaLinux 8"
---

## a) Configuring the _OpenSSH_ Server

Open the **/etc/ssh/sshd_config** file in your preferred text editor with superuser privileges. Find the **AllowTcpForwarding** parameter and change its value to **no**:

```conf
AllowTcpForwarding no
```

## b) Restarting the _OpenSSH_ Server

Restart the _sshd_ **service** to apply the change:

```sh
sudo systemctl restart sshd.service
```

This will perform a graceful restart of the SSH server.

---

## Documentation

- <https://linux.die.net/man/5/sshd_config>

---
date: "2022-08-05T20:43:00+00:00"
title: "How to Enable Remote Access to MariaDB Database Server on AlmaLinux 8"
---

**Previous:** _<https://bitscoper.dev/posts/how-to-setup-mariadb-database-server-on-almalinux-8>_

---

## a) Configuring

Edit the **/etc/my.cnf.d/mariadb-server.cnf** file in your preferred text editor with superuser privileges.

Suppose you want the _MariaDB_ server to listen on address **0.0.0.0** and port **12345**. Under the **[mysqld]** section, add or edit the following lines:

```conf
bind-address=0.0.0.0

port=12345
```

The address **0.0.0.0** means **all available IP addresses**, including **localhost**. If you want to bind only a single IP address, specify that address instead. If the port is not defined, the server listens on its default port **3306**.

## b) Restarting

Restart the _mariadb_ **service**:

```sh
sudo systemctl restart mariadb.service
```

## c) Adding the Port to _SELinux_ Policy Configuration

Add the port to the _SELinux_ (Security-Enhanced Linux) policy configuration:

```sh
sudo semanage port -a -t mysqld_port_t -p tcp 12345
```

## d) Making _FirewallD_ Allow the Port

Add the port to the _FirewallD_ allow list:

```sh
sudo firewall-cmd --zone=public --permanent --add-port=12345/tcp
```

Then reload _firewalld_:

```sh
sudo firewall-cmd --reload
```

---

**Next:** _<https://bitscoper.dev/posts/how-to-grant-remote-login-privilege-to-a-mariadb-user-account>_

---

## Documentation

- <https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/>

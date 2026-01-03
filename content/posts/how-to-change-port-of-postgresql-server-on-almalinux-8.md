---
date: "2023-04-14T05:10:40+00:00"
title: "How to Change Port of PostgreSQL Server on AlmaLinux 8"
---

## a) Edit Configuration File

Open the **/var/lib/pgsql/data/postgresql.conf** file in your preferred text editor with superuser privileges. Find and uncomment the following line:

```conf
# Port = 5432
```

Change the value to your desired port number. For example, to use port **1702**:

```conf
Port = 1702
```

## b) Let _FirewallD_ Know

If you require remote access, add the new port to _FirewallD_’s allow list:

```sh
sudo firewall-cmd --permanent --add-port=1702/tcp
```

Remove the default PostgreSQL port from the allow list:

```sh
sudo firewall-cmd --permanent --remove-port=5432/tcp
```

Then reload _FirewallD_:

```sh
sudo firewall-cmd --reload
```

## c) Restart _PostgreSQL_

Restart the database server to apply the changes:

```sh
sudo systemctl restart postgresql.service
```

---

## Documentation

- <https://www.postgresql.org/docs/current/runtime-config-connection.html>

---
date: "2022-11-14T21:03:00+00:00"
title: "How to Setup Lynis Security Auditor on AlmaLinux 8"
---

### a) Adding Repository

At first, you may need to add the official repository of the _Lynis_. So, create the **/etc/yum.repos.d/cisofy-lynis.repo** file on your favorite text editor with superuser privileges and populate it with the information below.

```ini
[lynis]
name=CISOfy Software - Lynis package
baseurl=https://packages.cisofy.com/community/lynis/rpm/
enabled=1
gpgkey=https://packages.cisofy.com/keys/cisofy-software-rpms-public.key
gpgcheck=1
priority=2
```

### b) Enabling Repository

Then enable the repository.  
`sudo yum-config-manager --enable lynis`

### c) Installing

Now, install the _Lynis_.  
`sudo yum install lynis`

### d) Usage

Run an audit on your lovely system.  
`sudo lynis audit system`

---

### Documentation

- <https://cisofy.com/documentation/lynis/>

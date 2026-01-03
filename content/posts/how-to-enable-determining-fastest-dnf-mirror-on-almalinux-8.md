---
date: "2022-07-10T20:37:00+00:00"
title: "How to Enable Determining Fastest DNF Mirror on AlmaLinux 8"
---

Open the **/etc/dnf/dnf.conf** file in your preferred text editor with superuser privileges.

Under the **[main]** section, add or edit the following boolean parameter:

```conf
fastestmirror=1
```

You do not need to reload or restart any service manually. Simply update the package database:

```sh
sudo dnf update
```

_DNF_ will determine the fastest mirror for the repositories based on both latency and download speed, and then proceed with the update.

Enjoy!

---

## Documentation

- <https://dnf.readthedocs.io/en/latest/conf_ref.html>

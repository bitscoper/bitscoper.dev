---
date: "2023-10-25T00:11:19+00:00"
title: "How to Change GRUB Timeout on Debian 12 Bookworm"
---

## a) Configuring GRUB

Open the **/etc/default/grub** file in your preferred text editor with superuser privileges and edit the following value:

```sh
GRUB_TIMEOUT=5
```

This value specifies the time, in seconds, to wait for keyboard input before booting the default menu entry.

- **0** — boot immediately  
- **-1** (unset) — wait indefinitely

## b) Updating GRUB

After making changes, update the GRUB configuration:

```sh
sudo update-grub
```

or:

```sh
sudo update-grub2
```

Both commands perform the same action. The update process may take some time to complete.

---

## Documentation

- <https://www.gnu.org/software/grub/manual/grub/html_node/timeout.html>
- <https://www.gnu.org/software/grub/manual/grub/html_node/Simple-configuration.html>

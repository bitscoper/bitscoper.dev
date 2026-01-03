---
date: "2023-11-11T01:00:53+00:00"
title: "How to Fix Broken Bangla Font on Debian 11 Bullseye or 12 Bookworm"
---

## a) Installing Google Noto Fonts

Install the required _Google Noto_ font packages:

```sh
sudo apt install fonts-noto-core fonts-noto-ui-core
```

## b) Removing Conflicting Fonts

Remove the conflicting _FreeSans_ and _FreeSerif_ font families:

```sh
sudo rm -f /usr/share/fonts/truetype/freefont/FreeSans* && sudo rm -f /usr/share/fonts/truetype/freefont/FreeSerif*
```

## c) Updating Font Cache

Update the font cache:

```sh
fc-cache -f -v
```

You may need to restart your applications for the changes to take effect. If the issue persists, try rebooting your system.

---

We love Bangla!

---

## Resources

- <https://linux.die.net/man/1/fc-cache>
- <https://fonts.google.com/noto>

---
date: "2024-03-17T16:57:53+00:00"
title: "How to Install Additional Codecs on Fedora Linux"
---

Install the packages and enjoy!

```sh
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-plugin-libav --exclude=gstreamer1-plugins-bad-free-devel

sudo dnf install lame\* --exclude=lame-devel

sudo dnf group upgrade --with-optional Multimedia
```

---

### Documentation

- <https://docs.fedoraproject.org/en-US/quick-docs/installing-plugins-for-playing-movies-and-music/>

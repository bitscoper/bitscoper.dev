---
date: "2024-10-07T14:20:54+00:00"
title: "How to Fix GNOME Camera (Snapshot) Not Detecting Webcam on Arch LInux"
---

Add yourself to the `video` group:

```sh
sudo usermod -aG video $USER
```

Reboot your system or log out and log back in to apply the change.

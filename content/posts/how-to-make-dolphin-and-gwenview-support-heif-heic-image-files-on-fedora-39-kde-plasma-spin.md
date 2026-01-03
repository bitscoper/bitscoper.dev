---
date: "2023-11-25T19:33:55+00:00"
title: "How to Make Dolphin and Gwenview Support HEIF/HEIC Image Files on Fedora 39 KDE Plasma Spin"
---

HEIF stands for the standard: High Efficiency Image Format; while HEIC is _Apple_'s chosen file name extension.  
On Fedora 39 KDE Plasma spin, its _Dolphin_ file manager and _Gwenview_ image viewer don't support HEIF/HEIC image files. You can solve the problem easily.

### a) Installing

Install a package named _libheif-freeworld_.  
`sudo dnf install libheif-freeworld`

### b) Refreshing

Refresh/reload/restart your _Dolphin_ file manager or _Gwenview_ image viewer or the software you want to take effect.  
Enjoy!

---
date: "2023-09-15T22:10:43+00:00"
title: "How to Enable Video Thumbnails in Nautilus File Manager on Fedora Workstation 38"
---

## a) Installing _FFmpegthumbnailer_

Install the _ffmpegthumbnailer_ package:

```sh
sudo dnf install ffmpegthumbnailer
```

## b) Cleaning Cached Thumbnail Files

Remove the cached thumbnail files from your home directory:

```sh
rm -rf ~/.cache/thumbnails
```

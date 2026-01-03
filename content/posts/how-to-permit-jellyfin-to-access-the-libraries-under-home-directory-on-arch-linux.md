---
date: "2024-03-03T15:25:15+00:00"
title: "How to Permit Jellyfin to Access the Libraries Under Home Directory on Arch Linux"
---

In order to add a directory to a _Jellyfin_ library, it needs to access the directory and all its parent directories. So, if you add `~/Media` to a library, _Jellyfin_ fails to access it.

### Permitting Access

To fix it, grant _Jellyfin_ execution permission for your home directory. It runs as user _jellyfin_.  
`setfacl --modify user:jellyfin:--x ~`

Now, the media server can access not only `~/Media` but also other directories under `~`, which is **unsafe**.

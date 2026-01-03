---
date: "2024-04-07T20:11:19+00:00"
title: "How to Disable Building -debug Packages by yay or paru on Arch Linux"
---

Open the **/etc/makepkg.conf** file in your preferred text editor with superuser privileges and search for `OPTIONS`. It may look like the following:

```conf
OPTIONS=(strip docs !libtool !staticlibs emptydirs zipman purge debug lto)
```

Now append a NOT—an exclamation mark (`!`)—before `debug`, so it becomes:

```conf
!debug
```

After making this change, try installing an _AUR_ package. The `-debug` packages will no longer be built.

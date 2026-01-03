---
date: "2024-01-01T19:38:48+00:00"
title: "How to Fix XPCOMGlueLoad Error of Tor Browser Due to Missing libdbus-glib-1.so.2 File on Fedora 39 KDE Plasma Spin"
---

If you install the _Tor Browser_'s launcher via `sudo dnf install torbrowser-launcher` and then installed the browser via the launcher on a freshly installed _Fedora 39 KDE Plasma Spin_ system, you may encounter this problem. In this scenario, the browser can not be launched and CLI says (with `--verbose`):

```log
XPCOMGlueLoad error for file /home/$USER/.local/share/torbrowser/tbb/x86_64/tor-browser/Browser/libxul.so:
libdbus-glib-1.so.2: cannot open shared object file: No such file or directory
Couldn't load XPCOM.
```

The solution is easy as follows.

### Installing Missing Dependency

Install a package named `dbus-glib`.  
`sudo dnf install dbus-glib`

Retry to launch the browser now.

---
date: "2022-12-13T21:08:00+00:00"
title: "How to Solve Cockpit OSTree Unavailability Error on Fedora Server"
---

**Previous:** [How To Setup Cockpit On Fedora Server](https://bitscoper.dev/posts/how-to-setup-cockpit-on-fedora-server)

---

In [this post](https://bitscoper.dev/posts/how-to-setup-cockpit-on-fedora-server), you learned that you can install all plugins of _Cockpit_ by wildcard.  
`sudo dnf install cockpit-*`  

This attempt installs the **_cockpit-ostree_** package on your _Fedora Server_, which does not use **_rpm-ostree_** to manage its packages. But **_cockpit-ostree_** is only intended for use on distributions that use **_rpm-ostree_**, such as _Fedora Silverblue_, _Fedora Kinoite_, _Fedora IoT_, _Fedora CoreOS_, and a small subset of _RHEL_ that uses **_rpm-ostree_**. Your system should be using _Cockpit_’s _PackageKit_-based software updater instead.

### Solution

Just remove the **_cockpit-ostree_** package.  
`sudo dnf remove cockpit-ostree`  

You don’t need to reload the _Cockpit_ **socket**.

---

### Documentation

- <https://cockpit-project.org/faq.html>

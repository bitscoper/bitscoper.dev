---
date: "2024-03-03T15:09:55+00:00"
title: "How to Fix the Native-Messaging Problem of LibreWolf Extensions on Arch Linux"
---

If you install _LibreWolf_ from _AUR_ via `yay -S librewolf-bin`, you may find that some extensions are not able to communicate with native applications.

### The fix that worked for me

```sh
sudo ln -s /usr/lib/mozilla/native-messaging-hosts /usr/lib/librewolf/native-messaging-hosts
```

---

### References

- <https://gitlab.com/librewolf-community/browser/linux/-/issues/250>
- <https://codeberg.org/librewolf/issues/issues/580>

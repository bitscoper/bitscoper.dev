---
date: "2024-04-07T19:35:48+00:00"
title: "How to Enable Automatic Word Wrapping on Visual Studio Code (VS Code) or VSCodium"
---

Press **Ctrl + Shift + P** and search for _**Preferences: Open User Settings (JSON)**_.

On Linux, you may also find the file at the following path:

```text
/home/$USER/.config/Code/User/settings.json
```

Add or edit the following value and set it to `"on"`:

```json
{
  "editor.wordWrap": "on"
}
```

---

Enjoy coding!

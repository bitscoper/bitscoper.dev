---
date: "2023-12-03T01:09:18+00:00"
title: "How to Sort GNOME 45 App Picker Entries Alphabetically on Fedora Workstation 39"
---

### a) Configuring

Set the value “ **[]**” on **app-picker-layout** of **org.gnome.shell** in the _dconf_ configuration database.  
`gsettings set org.gnome.shell app-picker-layout "[]"`  

You can also do it in the graphical way instead of the command line by using a GUI application named _dconf-editor_.

### b) Restarting

Restart your cute _GNOME_ shell by logging out and then logging in. Or you can simply restart your lovely system.  
Then you will find your _GNOME_‘s _App Picker_ sorting the entries **alphabetically** every time.

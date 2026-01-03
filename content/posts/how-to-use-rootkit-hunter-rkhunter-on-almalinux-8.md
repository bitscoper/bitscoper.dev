---
date: "2023-01-16T21:14:00+00:00"
title: "How to Use Rootkit Hunter (rkhunter) on AlmaLinux 8"
---

### a) Installing _Rootkit Hunter_

Install _Rootkit Hunter_ which is available as _rkhunter_ package.  
`sudo dnf install rkhunter`

### b) Updating Database

Before using, you need to update the database of _Rootkit Hunter_.  
`sudo rkhunter --update`  
With the database files refreshed, you can set your baseline file properties so that _Rootkit Hunter_ can alert you if any of the essential configuration files it tracks are altered. Tell _Rootkit Hunter_ to check the current values and store them as known-good values:  
`sudo rkhunter --propupd`

### c) Scanning

Start scanning your lovely system.  
`sudo rkhunter --check`

---

### Documentation

<https://sourceforge.net/p/rkhunter/wiki/index/>

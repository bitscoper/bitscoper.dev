---
date: "2022-09-18T20:51:00+00:00"
title: "How to Log Users Out of Shell Automatically When They Are Idle"
---

Here, we will be configuring the _Bash_ timeout for one user only.

### a) Configuring _Bash_

Open your **~/.bashrc** file on your favorite text editor with appropriate privileges and add or edit the following line. Here, we want to log us out after **2 minutes or 120 seconds** of idleness.  
`TMOUT=120`

### b) Reloading Configuration

You have to reload this modified configuration by sourcing your **~/.bashrc** file.  
`source ~/.bashrc`  
And it will take effect immediately.

---

### Documentation

- <https://www.gnu.org/software/bash/manual/bash.html#index-TMOUT>

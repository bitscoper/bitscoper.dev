---
date: "2024-03-17T17:08:17+00:00"
title: "How to Install From Lists Using pacman and yay or paru on Arch Linux"
---

### a) Making List of Packages

Create a plain text file containing the desired packages, separated by a new line.

```csv
arch-wiki-docs
dovecot
opendkim
php
php-fpm
php-gd
php-pgsql
postfix
postfix-pcre
postgresql
postgresql-docs
postgresql-ip4r
postgresql-libs
```

### b) Making List of _AUR_ Packages

Create a plain text file containing the desired packages, separated by a new line.

```csv
bitscoper-cyber-toolbox-bin
bitscoper-usb-logger
icecast
mistserver
satdump
sdrangel-bin
sdrpp-git
virtio-win-stable
zenmap
```

### c) Installing the Packages

Pass the lists to the _pacman_ and _yay_ or _paru_.  
`sudo pacman -S --needed - <./pacman_Packages.txt`  
and  
`yay -S --needed - <./AUR_Packages.txt`  
or  
`paru -S --needed - <./AUR_Packages.txt` **Do not run _yay_ with _sudo_!**

I used the following script.

```bash
#!/bin/bash

# By Abdullah As-Sadeed

if [ -n "$SUDO_USER" ]; then
    echo -e "\e[31mPlease do not run with sudo!\e[0m"
    exit
fi

# Install yay
if ! command -v yay &>/dev/null; then
    # Trace mode
    set -x

    git clone https://aur.archlinux.org/yay-bin.git

    cd yay-bin || exit

    makepkg -si

    cd ..

    rm -rf yay-bin
fi

# Trace mode if not set
if [[ "$(set -o | grep xtrace)" == *"off"* ]]; then
    set -x
fi

sudo pacman -Syyu

sudo pacman -S --needed - <./pacman_Packages.txt

yay -S --needed - <./AUR_Packages.txt

sudo pacman -Rsn - <./Unwanted_pacman_Packages.txt

sudo pacman -Rns $(sudo pacman -Qtdq)

yay -Scc
```

---

> “I used Arch BTW!”

---
date: "2024-03-03T16:42:28+00:00"
title: "How to Mount LUKS2-Encrypted Storage on Arch Linux"
---

### a) Decrypting Partition

In this example, the **/dev/sda** device has the partition **/dev/sda1** which is LUKS2-encrypted. Now, decrypt it. You will be prompted to enter the passphrase.  
`sudo cryptsetup luksOpen /dev/sda1 Target_Name`  
The target can be named anything.

### b) Creating Mount Point

Create a mount point by either:  
`sudo mkdir /run/media/$USER/` and  
`sudo mkdir /run/media/$USER/Mount_Point`  
or:  
`sudo mkdir /mnt/Mount_Point`

### c) Mounting Partition

`sudo mount /dev/mapper/Target_Name /run/media/$USER/Mount_Point`  
or  
`sudo mount /dev/mapper/Target_Name /mnt/Mount_Point`

### d) Fixing Permission

If you are unable to access the mounted partition, you can try the following approach, although **it may be a bad practice**.  
`sudo chown -R $USER /run/media/$USER/Mount_Point`  
or  
`sudo chown -R $USER /mnt/Mount_Point`

---

Enjoy encryption!

---

### Documentations

- <https://www.man7.org/linux/man-pages/man8/cryptsetup.8.html>
- <https://www.man7.org/linux/man-pages/man8/mount.8.html>

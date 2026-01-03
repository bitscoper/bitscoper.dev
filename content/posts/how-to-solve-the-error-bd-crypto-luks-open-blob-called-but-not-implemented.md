---
date: "2022-12-23T21:10:00+00:00"
title: "How to Solve the Error “bd_crypto_luks_open_blob called, but not implemented”"
---

The mentioned error appears when attempting to open LUKS2 (Linux Unified Key Setup) encrypted devices using _PCManFM-Qt_ file manager in _Lubuntu 18.04 LTS (Bionic Beaver)_. But it’s easy to solve, don’t worry.

### a) Installing

Actually you need a package named _libblockdev-crypto2_.  
`sudo apt install libblockdev-crypto2`

### b) Restarting

Then restart _udisks2.service_.  
`sudo systemctl restart udisks2.service`  

The problem should be solved now. Try mounting the desired device again.

---

### Documentation

- <https://packages.ubuntu.com/bionic/libblockdev-crypto2>

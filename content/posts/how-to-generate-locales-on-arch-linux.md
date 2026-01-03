---
date: "2024-03-03T16:09:11+00:00"
title: "How to Generate Locales on Arch Linux"
---

Locale names are typically of the form `language[_territory][.codeset][@modifier]`, where language is an _ISO 639 language code_, territory is an _ISO 3166 country code_, and codeset is a character set or encoding identifier.

### a) Listing the Enabled Locales

`locale -a`  
The output may look like this:

```text
ar_SA.utf8
bn_BD
bn_BD.utf8
C
C.utf8
en_GB.utf8
en_US.utf8
POSIX
ru_RU.utf8
```

### b) Selecting Locales

Edit the **/etc/locale.gen** file on your favorite text editor with superuser privileges, uncomment the desired entries, and comment out or leave commented the non-applicable entries.

```text
.......
ar_SA.UTF-8 UTF-8
#ar_SA ISO-8859-6
bn_BD UTF-8
#bn_IN UTF-8
en_GB.UTF-8 UTF-8
#en_GB ISO-8859-1
en_US.UTF-8 UTF-8
#en_US ISO-8859-1
#ru_RU.KOI8-R KOI8-R
ru_RU.UTF-8 UTF-8
#ru_RU ISO-8859-5
.......
```

_UTF-8_ is recommended over other character sets.

### c) Generating Locales

Run to generate the enabled locales.  
`sudo locale-gen`  

_locale-gen_ also runs with every update of _glibc_.

---

### Documentation

- <https://wiki.archlinux.org/title/Locale>

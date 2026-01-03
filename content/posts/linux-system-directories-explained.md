---
date: "2025-01-26T13:15:57+00:00"
title: "Linux System Directories Explained"
---

The Linux filesystem follows a meticulously structured hierarchical architecture designed to optimize organization.

## 1. The Root Directory

The root directory (`/`) serves as the primary node from which all subordinate directories and files emanate.

## 2. System Directories

- `/bin` — Contains essential user-level binary executables required for fundamental system operations, including core utilities such as `ls` and `cp`.
- `/sbin` — Houses administrative binary executables typically reserved for superuser privileges, including tools like `fdisk` and `fsck`.
- `/boot` — Stores critical boot components such as kernel images, initial RAM disk images (`initrd` or `initramfs`), and bootloader configurations (e.g., GRUB or LILO).
- `/dev` — Contains device nodes that interface with hardware and pseudo-devices, including block devices (`/dev/sda`), character devices (`/dev/tty`), and special system interfaces.
- `/etc` — Central location for system-wide configuration files governing authentication, networking, services, and daemon behavior.
- `/home` — Repository for individual user environments, including personal data, user-specific configuration files, and isolated workspaces.
- `/lib` and `/lib64` — Store **dynamically linked libraries** and kernel modules required for executing both system and user binaries.
- `/media` — Acts as an automatic mount point for removable media such as USB drives and optical discs.
- `/mnt` — Provides a temporary mount location for manually mounted filesystems and network shares.
- `/opt` — Reserved for optional, third-party, or proprietary software that does not conform to the native package management hierarchy.
- `/proc` — A virtual pseudo-filesystem exposing real-time kernel and process information.
- `/root` — The home directory of the root user, separate from regular user directories located under `/home`.
- `/run` — A **volatile** directory holding runtime data such as process IDs (PIDs), sockets, and interprocess communication files.
- `/srv` — Intended for server-specific data such as web service roots (`/srv/www`) or FTP content.
- `/sys` — A virtual filesystem providing access to kernel objects, device parameters, power states, and system controls via `sysfs`.
- `/tmp` — Temporary storage for **transient files**, typically cleared on reboot.
- `/usr` — Contains user-level applications, libraries, and shared resources, including `/usr/bin`, `/usr/lib`, and `/usr/share/man`.
- `/var` — Stores variable, mutable data such as logs (`/var/log`), spool files (`/var/spool`), and application caches (`/var/cache`).

## Documentation

- <https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard>

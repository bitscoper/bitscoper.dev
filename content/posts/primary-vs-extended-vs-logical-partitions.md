---
date: "2025-03-24T18:06:26+00:00"
title: "Primary vs. Extended vs. Logical Partitions"
---

Disk partitioning divides a storage device into isolated sections, each serving a specific purpose. The three classic partition types—**primary**, **extended**, and **logical**—are most relevant to MBR-based partitioning schemes.

## Primary Partition

A **primary partition** is a top-level partition on a storage device. These partitions are typically used to install the **operating system (OS)** and essential system files.

- A disk can contain up to **four primary partitions** under the MBR scheme.
- One primary partition can be marked as **active** and used for booting.

## Extended Partition

An **extended partition** is a special type of primary partition that acts as a **container** for logical partitions.

- Only **one extended partition** can exist per disk.
- It does not store data directly.
- It is used to overcome the four-primary-partition limitation of MBR.

## Logical Partition

**Logical partitions** are subdivisions created **inside the extended partition**.

- Multiple logical partitions can exist within a single extended partition.
- Each logical partition behaves like an independent disk, allowing separate filesystems.
- They provide flexibility for organizing data beyond primary partition limits.

## Summary

Primary partitions host operating systems, extended partitions enable expansion, and logical partitions provide scalable storage organization within that extended space.

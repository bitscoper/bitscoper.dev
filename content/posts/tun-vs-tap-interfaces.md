---
date: "2025-03-10T11:33:56+00:00"
title: "TUN vs. TAP Interfaces"
---

**TUN** and **TAP** are virtual network interfaces that operate at different layers of the OSI network stack, making them suitable for distinct networking use cases.

## Position in the Network Stack

- **TAP interfaces**  
  Operate at **Layer 2 (Data Link / Ethernet)**, allowing them to handle Ethernet frames and **non-IP protocols** such as LLDP, NetBEUI, and Banyan VINES.

- **TUN interfaces**  
  Operate at **Layer 3 (Network / IP)** and are limited to **IPv4 and IPv6** traffic.

## Traffic Handling

- **TAP interfaces**  
  Their lower position in the stack allows them to transport non-IP traffic and **support bridging**, enabling integration with physical Ethernet interfaces.

- **TUN interfaces**  
  Restricted to IP traffic and **cannot participate in Ethernet bridging**, as they do not process Layer 2 frames.

## Mechanisms

- **MAC addressing and ARP (TAP)**  
  TAP interfaces are assigned **MAC addresses** and use **ARP** to map IP addresses to MAC addresses, encapsulating IP packets inside Ethernet frames.

- **Packet handling efficiency (TUN)**  
  TUN interfaces operate directly on IP packets, eliminating the need for Ethernet framing and ARP, which improves efficiency.

## Performance

TUN interfaces generally offer **better performance** for pure IP routing due to reduced overhead. TAP interfaces introduce additional overhead by encapsulating traffic at Layer 2.

## Use Cases

- **TAP interfaces**  
  Best suited for scenarios involving **bridging**, **network emulation**, **traffic analysis**, or **legacy protocol support**.

- **TUN interfaces**  
  Commonly used in **VPN implementations** to securely route IPv4 or IPv6 traffic between endpoints.

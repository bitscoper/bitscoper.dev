---
date: "2025-03-03T17:39:44+00:00"
title: "How IPsec Impacts MSS and MTU"
---

IPsec introduces changes to the **Maximum Transmission Unit (MTU)** and **Maximum Segment Size (MSS)**, both of which are critical considerations for network performance and reliability.

## MTU Impact

The MTU is effectively **reduced** when IPsec is implemented due to encapsulation overhead. This overhead, which includes encryption data and additional IP headers, typically adds approximately **93 bytes** to each packet.

Assuming a standard Ethernet MTU of **1500 bytes**, this results in an effective MTU of roughly **1407 bytes**. Packets exceeding this size must be fragmented, which can lead to reduced performance, increased latency, or packet loss, as fragments are more susceptible to transmission issues.

## MSS Impact

The MSS (Maximum Segment Size) represents the maximum amount of TCP payload data, excluding IP and TCP headers.

In IPsec-enabled environments, an MSS value of approximately **1400 bytes** is commonly observed, with TCP MSS often adjusted to around **1360 bytes** to safely accommodate IPsec overhead. Payloads exceeding this size are segmented into smaller packets or may be dropped, negatively impacting throughput and efficiency.

## Summary

Both MTU and MSS are **reduced** as a result of IPsec’s encapsulation process. Proper adjustment of MTU and TCP MSS values is essential to prevent fragmentation, maintain optimal performance, and ensure reliable data transmission across IPsec-secured networks.

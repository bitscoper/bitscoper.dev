---
date: "2025-03-02T13:37:08+00:00"
title: "TCP vs. UDP: Comparison Table"
---

| Factor | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
|------|-------------------------------------|------------------------------|
| **Connection Type** | Connection-oriented; requires a handshake before data transfer | Connectionless; data can be sent without prior setup |
| **Data Ordering** | Guarantees in-order delivery of data | Does not guarantee ordering |
| **Retransmission** | Retransmits lost or corrupted packets | No retransmission of lost packets |
| **Reliability** | Reliable delivery is guaranteed | Delivery is best-effort, not guaranteed |
| **Error Checking** | Comprehensive error detection and correction | Basic error detection only |
| **Flow & Congestion Control** | Built-in flow and congestion control mechanisms | No flow or congestion control |
| **Broadcast / Multicast** | Not supported | Supported |
| **Speed & Overhead** | Slower due to reliability mechanisms and overhead | Faster with low overhead |
| **Common Use Cases** | Web browsing (HTTP/HTTPS), email, file transfers | Streaming, VoIP, online gaming, DNS |

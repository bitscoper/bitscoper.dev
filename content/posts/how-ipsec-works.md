---
date: "2025-03-03T13:58:08+00:00"
title: "How IPsec Works"
---

IPsec (Internet Protocol Security) is a core protocol suite used to safeguard communications over IP networks. Understanding how IPsec operates is essential when configuring or troubleshooting secure network connections such as VPNs.

IPsec functions at the **Network Layer (Layer 3)** of the OSI model, allowing organizations to secure traffic between entire networks rather than individual applications. End users typically access IPsec-protected networks through a VPN client, which establishes a secure tunnel to a remote gateway.

## Stage 1: Traffic Identification (Host Recognition)

Before packets enter an IPsec tunnel, the host evaluates outgoing traffic against defined **IPsec policies** to determine which packets require protection.

Packets selected for IPsec processing are encapsulated with:

- A new IP header
- Authentication headers (AH) and/or
- Encryption headers (ESP)

These headers allow the receiving host to authenticate the sender, verify packet integrity, and decrypt the payload.

## Stage 2: Negotiation (IKE Phase 1)

Before secure communication begins, both endpoints must agree on security parameters. This negotiation is handled by **Internet Key Exchange (IKE)**, typically **IKEv2** in modern implementations.

During this phase, peers negotiate:

- Encryption algorithms
- Hashing algorithms
- Authentication methods
- Diffie-Hellman groups

> **Note:** Main mode and aggressive mode apply to **IKEv1**, not IKEv2. IKEv2 simplifies negotiation into fewer, more secure message exchanges.

## Stage 3: Establishing the IPsec Tunnel (IKE Phase 2)

Once IKE negotiation completes, the endpoints establish **Security Associations (SAs)** that define how traffic will be protected.

During this stage:

- Session-specific encryption keys are generated
- Cryptographic nonces ensure freshness and prevent replay attacks
- Parameters for ESP or AH are finalized

Both hosts now possess the necessary cryptographic material to securely exchange data.

## Stage 4: Secure Data Transmission

With the IPsec tunnel established, data is transmitted securely using:

- **ESP (Encapsulating Security Payload)** for encryption and integrity
- Either **transport mode** (host-to-host) or **tunnel mode** (gateway-to-gateway)

While IPsec itself operates over IP, **UDP encapsulation (NAT-T)** may be used to traverse NAT devices and firewalls, commonly over UDP port 4500.

## Stage 5: Session Termination

An IPsec session ends when a predefined time limit or data threshold is reached. Upon termination:

- Security Associations are deleted
- Encryption keys are securely discarded

This prevents key reuse and reduces the risk of replay or spoofing attacks after the session ends.

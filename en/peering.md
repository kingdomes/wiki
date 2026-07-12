---
title:  Peer with me
description: 
published: true
date: 2026-07-12T08:27:55.600Z
tags: 
editor: markdown
dateCreated: 2026-07-12T08:27:55.600Z
---

# Peering with Me

This page provides introductory information about peering with **AFNOOI-Network**.

---

## Overview

AFNOOI-Network welcomes DN42 community members to establish peering. We maintain an open and friendly peering policy, committed to building a stable, low-latency network topology.

---

## Peering Requirements

Before initiating a peering request, please confirm that you meet the following basic requirements:

| Item | Requirement |
| :--- | :--- |
| **ASN** | A valid DN42 ASN |
| **IP Prefixes** | At least one IPv4 and/or IPv6 prefix |
| **Tunnel Protocol** | Support for WireGuard or GRE tunnels |
| **BGP Protocol** | Support for BGP (BIRD or FRRouting recommended) |
| **Network Stability** | A relatively stable network connection to avoid frequent flapping |

---

## Supported Tunnel Protocols

| Protocol | Description |
| :--- | :--- |
| **WireGuard** | Recommended protocol, simple configuration, high security |
| **GRE** | Standard GRE tunnel support |

> *If you require another protocol, please discuss it in advance.*

---
## Tunnel Configuration
Only the following network ranges will be forwarded over the dn42 network. All other traffic will be dropped ~~(eaten)~~.

- DN42 block IPv4 172.16.0.0/12  IPv6 fd00::/8 
- NEO block IPv4 10.0.0.0/8  ~~IPv6 fd00::/8~~
---
## BGP Configuration
| ASN | NET |Who|
| :--- | :--- | :--- |
| AS4242422213 | DN42 |AFNOOI-MNT|
| AS4242422213 | DN42 |ISWALL-MNT and AFNOOI-MNT|
| AS4201270009 | NEO |AFNOOI|
---
## BGP Feature Support

The AFNOOI-MNT network uses **BIRD 2** and supports the following features:

| Feature | Description | RFC |
| :--- | :--- | :--- |
| **Multiprotocol BGP** | Multiprotocol BGP | RFC 4760 |
| **BGP Large Communities** | BGP Large Communities | RFC 8092 |
| **BGP Confederations** | BGP Confederations | RFC 5065 |
| **Extended Next Hop** | Extended Next Hop | RFC 5549 |
| **Extended Messages** | Extended Messages | RFC 8654 |
| **dn42 ROA** | dn42 Route Origin Authorisation (see Route Filtering below) | — |
| **dn42 Route Origin Community** | dn42 Route Origin Community | — |

---

## Default Extensions

- **Multiprotocol BGP** is the preferred protocol and is **enabled by default**. If you cannot support multiprotocol BGP sessions, please let us know when peering.
- **Extended Next Hop** and **Extended Messages** are both **enabled by default**.

---

## Route Filtering

This network applies strict **Route Origin Authorisation (ROA)** filtering to all received and exported routes.

### Filtering Rules

- Any announced route that does **not have a corresponding `route` / `route6` object** in the dn42 registry **will be dropped** ~~(eaten)~~.
- ROA is implemented via RPKI, using `dn42regsrv` and `stayrtr` for data updates.

> dn42 ROA data is provided as a public service. For more details, see the [DN42 Services page](https://wiki.dn42/services).

---

### Allowed Prefixes

Routes within the following prefix ranges are allowed to be received and exported:

#### IPv4

- `172.20.0.0/14` and above (i.e. `/14`, `/15`, `/16` … `/32`)
- `10.0.0.0/8` and above (i.e. `/8`, `/9`, `/10` … `/32`)

#### IPv6

- `fd00::/8` with prefix length between `/44` and `/64`

> *Routes outside the above ranges will not be received or exported (~~they will be eaten~~).*

---

---
## Peering Process

1. **Confirm Information**: Check that you meet the peering requirements above.
2. **Submit Request**: Submit a peering request via IRC or email, including the following information:
   - Your ASN
   - The IP prefixes you wish to announce
   - Your WireGuard public key or GRE tunnel parameters
   - Your preferred BGP session settings (e.g., multihop, Keepalive timing, etc.)
3. **Negotiation and Configuration**: Both parties negotiate tunnel parameters and complete configuration.
4. **Testing and Verification**: Confirm that the BGP session is established and that route announcements are working properly.

---

## Contact

Please use the following channels to initiate a peering request:

- **Email**: `abuse@115411.xyz`
- **IRC**: `#AS4242422213` / `#dn42`
- **Tel**: `+042422131145` `+042422141145`
- **Fax**: `+042422131145` `+042422141145`

---

## FAQ

### Do you support multihop BGP?

Yes. Please let us know your preferred TTL and Keepalive settings in advance.

### Can I peer with an IPv6-only node?

Yes. We support IPv6 dual-stack and Extended Next-Hop.

---

## Disclaimer

AFNOOI-MNT reserves the right to adjust peering policies based on network conditions and actual circumstances.  
The information on this page is for reference only and is subject to the actual negotiated agreement.

---
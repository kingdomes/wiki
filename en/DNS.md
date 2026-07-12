---
title: DNS
description: 
published: true
date: 2026-07-12T08:31:53.006Z
tags: 
editor: markdown
dateCreated: 2026-07-12T08:31:53.006Z
---

# DNS

## Overview

AFNOOI-MNT maintains a set of DNS services for internal resolution within the DN42 network, aiming to provide stable and reliable domain name resolution support for the community.

## Supported Record Types

This DNS service is deployed on **Bind 9** and currently supports the following standard record types:

| Record Type | Description | Common Usage |
| :--- | :--- | :--- |
| **A** | IPv4 address record | Points a domain to an IPv4 address |
| **AAAA** | IPv6 address record | Points a domain to an IPv6 address |
| **CNAME** | Canonical name record | Alias one domain to another |
| **MX** | Mail exchange record | Specifies mail server address |
| **TXT** | Text record | Stores SPF, DKIM, verification info, etc. |
| **NS** | Name server record | Specifies the authoritative DNS servers for the domain |
| **PTR** | Pointer record | Enables reverse IP-to-domain lookups |
| **SOA** | Start of authority record | Defines domain management info (serial, refresh timers, etc.) |
| **NAPTR** | Naming authority pointer record | Used for ENUM (phone number mapping) and SIP routing |

---

## Public DNS Servers

The following DNS servers are open to the DN42 community and support recursive queries:

| Server | IPv4 | IPv6 | Type | Status | Location |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ns1.afn.dn42 | 172.23.57.130 | fdf1:8356:996d:1a3b:2c4d:5e6f:7081:92a3 | Recursive | Online | CN |
| ns2.af.dn42 | 172.23.57.131 | fdf1:8356:996d:b2c4:d5e6:f708:192a:3b4c | Recursive | Online | CN |
| ns3.af.dn42 | 172.23.57.132 | fdf1:8356:996d:7e8f:90a1:b2c3:d4e5:f607 | Authoritative | Online | CN |
| ns4.afn.dn42 | 172.23.57.148 | fdf1:8356:996d::1448 | Recursive | N/A | US |

---

## Supported Domain Suffixes

This DNS service supports resolution for the following domain zones:

- `*.afn.dn42`
- `*.afn.neo`
- `*.4.2.2.1.4.2.4.0.tel.dn42`
- `*.3.2.2.1.4.2.4.0.tel.dn42`
- `*.dn42` (partial cache forwarding)
- `*.neo` (partial cache forwarding)
- And more

To add your custom domain or subdomain, please contact the NOC team.

---

## Configuration Example

### Using `dig` to query

```bash
dig @ns1.afnooi.dn42 example.afn.dn42
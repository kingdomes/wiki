---
title: Public services
description: 
published: true
date: 2026-07-22T15:43:06.648Z
tags: 
editor: markdown
dateCreated: 2026-07-12T08:34:30.850Z
---

# Public Services

This page lists the public services provided by AFNOOI-Network to the DN42 community.

---

## Websites

| Service | Address |
| :--- | :--- |
| **Main Site** | `https://115411.xyz` |
| **Wiki** | `https://doot.uk.to` |
| **Status Page** | `https://uptime.115411.xyz` |

---

## Looking Glass

The Looking Glass service is used to view routing tables, BGP session status, and perform network connectivity tests.

| Service | Address |
| :--- | :--- |
| **Looking Glass** | `https://dn42.115411.xyz` |

### Usage

- Access via browser: `https://dn42.115411.xyz/[node]`
~~- Access via SSH: `ssh mnt@lg.dn42.115411.xyz` (please contact NOC for access permission)~~

---

## FlapAlerted

FlapAlerted is used to monitor route flapping.

| Service | Address |
| :--- | :--- |
| **FlapAlerted** | `https://fa-dn42.115411.xyz` |

---

## Auto-Peering

We provide an automated peering service for DN42 community members to simplify the connection process.

| Service | Address | Description |
| :--- | :--- | :--- |
| **Auto-Peer Endpoint** | `https://peer.115411.xyz` | Use this endpoint to automatically establish a BGP session with AFNOOI-Network |

### Usage

1.  Point your peering configuration to `peer.115411.xyz`.
2.  The system will automatically handle BGP session negotiation and establishment.
3.  For any issues, please contact the NOC via IRC or email.

---

## Pingable IP Addresses

The following IP addresses can be used for network connectivity tests:

I'm too lazy to write them out — please refer to [Node Information](https://doot.uk.to/en/nodes)
---
title: Dialing Service
description: 
published: true
date: 2026-07-12T08:36:38.641Z
tags: 
editor: markdown
dateCreated: 2026-07-12T08:36:38.641Z
---

# Dialing Services

This page introduces the VoIP dialing services provided by AFNOOI-Network within the DN42 network.

---

## Number Plan

All numbers are prefixed with `+04242213`, with the following allocation:

| Number | Function | Via | Description |
| :--- | :--- | :--- | :--- |
| `+042422131145` | Fax / Voice | Panasonic KX-FT982CN | Main number, supports both fax reception and voice calls |
| `+042422131146` | Fax / Voice | MicroSIP Client & FaxTalk | Windows MicroSIP & FaxTalk, supports fax, voice, and SMS reception |
| `+04242213110` | Voice Calls | Ordinary landline | Voice only — no fax support |
| `+0424221310086` | Balance Inquiry | IVR | Interactive Voice Response (IVR) system for checking account balance and phone numbers |

---

## Feature Descriptions

### Fax Service

- Supports **T.38** fax protocol (preferred) and **G.711** pass-through
- Faxes are automatically printed upon reception
- Supports CNG tone detection and automatic routing to fax handling

### Voice Service

- Built on **Asterisk** with **PJSIP**
- Supports IPv4 / IPv6 dual-stack ~~though connectivity isn't guaranteed~~
- Supports **ENUM** number resolution

### SMS Service

- `+042422131146` supports SMS reception (via MicroSIP client)

---

## Usage

### Inbound Routing

All numbers starting with `+04242213` are routed to the AFNOOI-MNT Asterisk server and forwarded to the corresponding endpoint or application based on the number allocation rules.

### Outbound Routing

- Uses **ENUM** queries to resolve destination numbers into SIP URIs
- Supports direct dialing to internal DN42 numbers

---

## Balance Inquiry

Dial `+0424221310086` and the system will announce your current account balance.

> The inquiry system currently only supports voice playback ~~and does not support SMS or email notifications~~.

---

## Technical Implementation

- **PBX Core**: Asterisk 20.6.0 + PJSIP
- **Fax Module**: `res_fax` / `app_fax` + T.38 ~~+ my fax machine~~
- **ENUM Resolution**: Based on DN42 internal recursive DNS
- **SMS Function**: `pjsip_messaging`

---

## Notes

- All services are only accessible within the **DN42 network**
- Please do not abuse these services for mass calling or fax bombing
- If you encounter any issues, feel free to contact the NOC via IRC, email, phone, or fax

---
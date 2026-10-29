<div align="center">

# Default Router Passwords: A Short Write-up

How a MAC address reveals a router's maker, and why unchanged default credentials are a real risk.

![Networking](https://img.shields.io/badge/Networking-ARP_·_OUI-30363D?style=flat-square)
![Security](https://img.shields.io/badge/Security_awareness-B22222?style=flat-square)

<sub>Personal write-up · For education only</sub>

</div>

> [!WARNING]
> Only test devices you own or are explicitly allowed to test. Logging in to someone else's router without permission is illegal in most countries.

## Overview

While studying networking at university I noticed how little effort it takes to identify a home router and find its factory password. This note walks through the reasoning step by step and ends with what owners should do about it.

## What I found

1. **The ARP table lists the gateway's MAC address.** Running `arp -a` shows the IP and MAC address of every device the machine has talked to recently, including the router.
2. **The first three bytes of a MAC address identify the manufacturer.** This prefix, the OUI, is public. Looking up `a8:6e:4e` on [maclookup.app](https://maclookup.app/macaddress/a86e4e) showed a Huawei device registered on 6 October 2020, which matched the HUAWEI WiFi AX3.
3. **Factory credentials are documented publicly.** Vendors and forums list the default logins for each model.
4. **One of those defaults still worked** on the admin page at the gateway address.

## Why it matters

Anyone already on the network, for example a guest on the Wi-Fi, can follow the same steps in a few minutes. With the admin page they can change DNS settings, open ports or lock the owner out.

## What to do

- Change the router's admin password on first setup, and use a long unique one.
- Keep the router's firmware up to date.
- Turn off remote administration unless you need it.
- Put guests on a separate guest network.

## Author

Yassine Aitaouicha

---

<div align="center"><sub>Part of <a href="https://github.com/creepout777">Yassine Aitaouicha's projects</a></sub></div>

## IP Address Structure

### What is an IP Address?

An **IP address** (Internet Protocol address) is a unique numerical label assigned to every device connected to a network. It serves two main purposes:

- **Host identification** - identifies a specific device on a network
- **Location addressing** - allows data to be routed to the correct destination
<br>

### The Two-Part Structure

Every IP address is divided into **two parts**:

#### Network Identifier (Network ID / Net ID)

- Identifies **which network** the device belongs to
- All devices on the same network share the same network identifier
- Used by routers to forward packets toward the correct network

#### Host Identifier (Host ID)

- Identifies a **specific device (host)** within that network
- Must be unique within its network
- Distinguishes individual machines from one another

### Analogy

Think of it like a postal address:

- **Network ID** = the street name / town (gets the letter to the right area)
- **Host ID** = the house number (gets the letter to the exact property)

### IPv4 Example

In the address `192.168.1.45` with subnet mask `255.255.255.0`:

- Network ID → `192.168.1`
- Host ID → `45`

---

## Subnet Masking

### What is Subnetting?

**Subnetting** is the process of dividing a larger network into smaller **sub-networks (subnets)**. This is done for:

- **Efficiency** - reduces unnecessary broadcast traffic
- **Security** -  isolates segments of a network from each other
- **Organisation** -  logically groups devices (e.g. by department or floor)
- **Better use of IP address space** - avoids wasting large blocks of addresses

### What is a Subnet Mask?

A **subnet mask** is a 32-bit number (in IPv4) used to identify **which part of an IP address is the network identifier** and which part is the host identifier.

- Bits set to **`1`** → part of the **network identifier**
- Bits set to **`0`** → part of the **host identifier**

### How It Works — Bitwise AND

To find the Network ID of a device, a **bitwise AND** operation is performed between the IP address and the subnet mask:

```
IP Address:    192.168.1.45   →  11000000.10101000.00000001.00101101
Subnet Mask:   255.255.255.0  →  11111111.11111111.11111111.00000000
                                  AND
Network ID:    192.168.1.0    →  11000000.10101000.00000001.00000000
```

The result tells routers which network the address belongs to.

### CIDR Notation

Subnet masks are often written in **CIDR (Classless Inter-Domain Routing)** notation as a suffix indicating how many bits are the network part:

|Subnet Mask|CIDR|Network Bits|Host Bits|Max Hosts|
|---|---|---|---|---|
|255.0.0.0|/8|8|24|16,777,214|
|255.255.0.0|/16|16|16|65,534|
|255.255.255.0|/24|24|8|254|
|255.255.255.128|/25|25|7|126|

> **Note:** 2 addresses are always reserved per subnet - one for the **network address** and one for the **broadcast address** - hence "Max Hosts = 2ⁿ − 2" where n = number of host bits.

### Default Gateway

Each subnet typically has a **default gateway** - the router interface that connects the subnet to other networks or the internet.

---

## IP Standards

### Two Current Standards: IPv4 and IPv6

#### IPv4 (Internet Protocol version 4)

- Introduced in **1981**
- Uses **32-bit** addresses
- Written as **four decimal octets** separated by dots: e.g. `192.168.0.1`
- Total possible addresses: **$2^{32}$ = ~4.3 billion**
- Developed when the internet was small

#### IPv6 (Internet Protocol version 6)

- Introduced in **1998**, deployment accelerated through the 2000s–2010s
- Uses **128-bit** addresses
- Written as **eight groups of four hexadecimal digits** separated by colons: e.g. `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- Total possible addresses: **$2^{128} \approx 3.4 \times 10^{38}$ (an astronomically larger number)
- Consecutive groups of all zeros can be shortened using `::` (once per address)

### Why Was IPv6 Introduced?

#### 1. IPv4 Address Exhaustion

The primary reason. With only ~4.3 billion addresses and billions of devices (smartphones, laptops, IoT devices, servers) all needing unique IPs, the IPv4 address pool was **exhausted** (IANA allocated the last block in **2011**).

#### 2. The Growth of the Internet of Things (IoT)

Modern homes and businesses contain many internet-connected devices (smart TVs, thermostats, fridges, etc.). IPv6 provides enough addresses to give every device its own globally unique IP.

#### 3. Removing the Need for NAT

IPv4 relied heavily on **NAT (Network Address Translation)** - a workaround that allows multiple devices to share one public IP. IPv6 eliminates this need, simplifying networking and enabling true end-to-end connectivity.

#### 4. Improved Features in IPv6

- **Simpler, more efficient packet headers** - faster routing
- **Built-in IPsec** - better security
- **Stateless Address Autoconfiguration (SLAAC)** - devices can self-assign addresses without a DHCP server
- **Better support for multicast** - more efficient than IPv4 broadcast

### Comparison Table

|Feature|IPv4|IPv6|
|---|---|---|
|Address size|32-bit|128-bit|
|Address format|Dotted decimal|Colon-separated hexadecimal|
|Total addresses|~4.3 billion|~3.4 × 10³⁸|
|Introduced|1981|1998|
|Header complexity|More complex|Simplified|
|NAT required?|Often yes|No|
|Security|Optional (IPsec)|Built-in (IPsec)|
|Auto-configuration|DHCP needed|SLAAC supported|

---

## Public and Private IP Addresses

### Public IP Addresses (Routable)

- **Globally unique** - no two devices on the internet can share the same public IP
- **Assigned by ISPs** (Internet Service Providers) from ranges allocated by IANA/RIPE etc.
- **Routable** on the internet - routers on the public internet can forward packets to these addresses
- Examples: `8.8.8.8` (Google DNS), `142.250.74.46` (Google)
- Used by web servers, routers' WAN interfaces, and any device that needs to be directly reachable over the internet

### Private IP Addresses (Non-Routable)

- **Not unique globally** - the same private IP can exist in millions of different private networks simultaneously
- **Not routable** on the public internet - internet routers will **drop** packets destined for private addresses
- Used **within local networks** (LANs) - homes, schools, businesses
- Assigned by a local router (usually via **DHCP**)

#### Reserved Private IP Ranges (IPv4)

|Range|CIDR|Typical Use|
|---|---|---|
|`10.0.0.0 – 10.255.255.255`|`10.0.0.0/8`|Large organisations|
|`172.16.0.0 – 172.31.255.255`|`172.16.0.0/12`|Medium networks|
|`192.168.0.0 – 192.168.255.255`|`192.168.0.0/16`|Home/small office|

> You will almost certainly recognise `192.168.x.x` - this is what home routers assign to devices on your home network.

### NAT — Network Address Translation

Because private addresses can't be routed over the internet, **NAT** is used by routers to translate between private and public addresses:

1. Device on private network sends a packet (from e.g. `192.168.1.5`)
2. The router **replaces the source IP** with its own public IP (e.g. `86.123.45.67`)
3. The router keeps a **translation table** to track which internal device sent which request
4. When a reply arrives at the public IP, the router translates it back and forwards it to the correct private device

This allows **many devices to share a single public IP address** - a critical workaround for IPv4 exhaustion.

NAT allows a pool of public IP addresses to be shared between private networks.

These pools of public addresses are held by internet service providers and allocated as needed to the private networks that connect their service

When a private network connects to the internet it is allocated a public address from the pool

Edge routers are what connects the private network to the ISP and has 2 addresses:

- A private address for the local network
- A public address for the internet

Packets going out to the internet with private address as its source will have its non-routable address swapped for the routable IP address

Packet details are stored in a NAT table

These details are a combination of the sending device’s private IP address together with a unique port number this is known as a socket

When the response to the request is received, the details from the NAT table are used to reinstate the correct local address. The response will then be directed to the right place

#### **Port forwarding:**

Port forwarding allows remote computers to connect to a specific computer or service within a private LAN

On a LAN, devices are configured with non-routable IP addresses which are not unique on the internet and so cannot be communicated with directly

access to the internet in a home network is provided by a network access device which is a combined device that provides a modem and a router as well as an ethernet switch and wireless access point

The network access device can be configured so that any traffic that arrives on a specific port is forwarded to a specific internal IP address

### Why the Distinction Matters

- **Security**: Private addresses are inherently hidden from the internet - external attackers cannot directly target a device with a private IP without first getting through the router
- **Address conservation**: NAT + private addressing extended the usable life of IPv4 by many years
- **Cost**: Public IPs (especially static ones) can cost money from an ISP; private IPs are free to use internally

### Loopback Address

A special address worth knowing: `127.0.0.1` (IPv4) or `::1` (IPv6) is the **loopback address**, used by a device to refer to itself. Traffic sent here never leaves the machine.

---

## Quick Summary

| Topic                | Key Point                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------- |
| IP Address Structure | Split into **Network ID** and **Host ID**                                                   |
| Subnet Masking       | Subnet mask uses 1s/0s to identify network vs host portion; bitwise AND extracts Network ID |
| IPv4                 | 32-bit, ~4.3 billion addresses, now exhausted                                               |
| IPv6                 | 128-bit, ~3.4×10³⁸ addresses, introduced due to IPv4 exhaustion + IoT growth                |
| Public IPs           | Globally unique, routable on the internet                                                   |
| Private IPs          | Non-routable, used within LANs, shared via NAT                                              |

- - -

## DHCP

Number of available private IP addresses within a private network is limited

DHCP is used to assign IP addresses to devices as they join a network.

DHCP uses a pool of available IP addresses to allocate IP addresses to new devices for the duration of their session.

The IP address is leased so that a computer cannot permanently hold on to an IP address so once a device leaves the network, the IP address that the device was using is returned to the pool for allocation to a new device.

After a certain amount of time (typically 24 hours), a new DHCP request needs to be made.

**The DORA Process (4 Phases):**

1. **D**iscover: Client searches for a DHCP server (broadcast) by broadcasts out a discover message for a DHCP server..
2. **O**ffer:  the Server sends an offer message of an IP address/lease,  the subnet mask, the lease duration, and the IP address of the DHCP server
3. **R**equest: Client requests to use the offered IP. If a network is configured with multiple DHCP servers, only one offer will be accepted.
4. **A**cknowledgement (ACK): Server confirms assignment. A packet is sent to the client that includes any other configuration information that the client requested.
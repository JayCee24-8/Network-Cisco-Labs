#📘 Module 7 – Routing (Static & RIP) Labs

This repository documents and explains hands-on labs for static and dynamic routing, including the configuration of RIP and floating static routes. Each lab includes objectives, key steps, results, and essential notes.

## 🧪 Labs Included

### 🔄 Lab 24 – Static Routing (Part 1)

**Objective:** Configure static routing between R1 and R2 to enable end-to-end connectivity between PCs.

**Result:** Verified that static routes allow PC1 and PC2 to communicate.

**Key Steps:**

Configure IP addresses on all interfaces.

Ping to identify reachability and trace issues.

Add static routes pointing to subnet networks.

** ⚠️ Notes: **

Initial pings from PC1 to PC2 fail due to routers not knowing the return route.

Use the correct CIDR notation when assigning addresses.

Use the show ip route command to verify learned routes.

Always set the next-hop to the neighbor’s IP, not the router’s own.

### 🔁 Lab 25 – Static Routing (Part 2)

**Objective: Extend static routing between multiple routers and allow multi-hop communication.

Result: Verified full connectivity among all PCs using intermediate routers.

Key Steps:

All IPs are preconfigured.

Add static routes via routers directly connected to destination subnets.

** ⚠️ Notes: **

R3 and R2 are not directly connected, so traffic must be routed via R1 or R4.

When routing through an intermediate router, use the IP address of the next reachable router.

Static routes must exist in both directions for full communication.

### 🌊 Lab 26 – Static Routing (Part 3): Floating Static Route

**Objective:** Configure a floating static route as a backup if the RIP-learned route fails.

**Result:** Successfully configured a floating static route with a higher administrative distance.

**Key Steps:**

RIP is configured on all routers except R1 and R3.

R1 learns about 10.0.0.0/24 via RIP (AD = 120).

We manually added a floating static route through R3 with AD = 130.

**⚠️ Notes:**

Floating static routes are used for backup and must have higher AD than the primary route.

If we use AD < 120, it overrides the RIP route and becomes the default.

Use the command:

ip route 10.0.0.0 255.255.255.0 192.168.13.3 130

Shutdown R2 to test the backup route.

Administrative Distance (AD) defines the trust level of a route. Lower AD = more preferred.

### 📡 Lab 27 – RIP (Part 1)

**Objective:** Enable RIP on R1 and R2 and verify dynamic route learning.

**Result:** Confirmed that R1 learned routes through RIP after enabling version 2 and disabling auto-summary.

Key Steps:

Configure RIP with router rip and network commands.

Initially, RIP v1 auto-summarizes to 10.0.0.0/8.

Enabling RIP v2 and disabling auto-summary fixes this.

**⚠️ Notes:**

Use RIP version 2 to support classless routing.

Use show ip route to verify learned subnets.

Enable version 2 with:

router rip
version 2
no auto-summary

### 🌐 Lab 28 – RIP (Part 2)

**Objective:** Configure RIP v2 on a more complex topology and verify end-to-end connectivity.

**Result:** All PCs successfully communicated across the network.

**Key Steps:**

Configure RIP on each router.

Disable updates on switch-connected interfaces using passive-interface.

Add all subnet-connected networks to RIP.

**⚠️ Notes:**

To avoid unnecessary RIP updates:

passive-interface [interface-type] [interface-number]

First pings may fail due to ARP and convergence delays.

##🔧 Skills Practiced

Configuring static routes using next-hop and exit interface

Understanding and applying administrative distance

Implementing RIP v1 and RIP v2

Identifying and solving one-way communication issues

Configuring floating static routes for redundancy

Using show and traceroute commands to verify connectivity

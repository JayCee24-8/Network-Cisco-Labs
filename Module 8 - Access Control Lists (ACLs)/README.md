# 📘 Module 8 – Access Control Lists (ACLs)
This module introduces Access Control Lists (ACLs) to control traffic in a network. It covers standard ACLs, extended ACLs, and named ACLs, demonstrating how to filter traffic based on source, destination, and protocol.

## 🧪 Labs Included
### 🔒 Lab 29 – Standard ACLs (ACLs Part 1)
**Objective:** Configure standard ACLs to restrict access so that only PCs in the 192.168.1.0/24 network can access SRV1, and block PC4 from communicating with the 192.168.1.0/24 network.
**Result:** Verified that only the allowed network had access to SRV1 and PC4 was successfully blocked.
**Key Steps:**
- Create a standard ACL to block PC4 (192.168.2.14) traffic.
- Apply ACL to R1’s interface towards the destination network.
- Allow all other traffic using permit any.

**⚠️ Notes:**
- Standard ACLs filter only by source IP address.
- They must be placed as close as possible to the destination to avoid blocking unintended traffic.
- Wildcard masks are the inverse of subnet masks.

### 🧩 Lab 30 – Extended ACLs (ACLs Part 2)
**Objective:** Configure extended ACLs so that only PC1 can access SRV1, and only hosts in 192.168.2.0/24 can access SRV2.
**Result:** Confirmed that ACLs correctly filtered traffic to servers, with specific hosts and subnets allowed while others were denied.
**Key Steps:**
- Define ACL rules with access-list 100 using permit ip for specific source/destination.
- Explicitly deny unwanted traffic.
- Apply the ACL to R1’s outbound interface towards R2.

**⚠️ Notes:**
- Extended ACLs filter by source + destination IP + protocol.
- They must be placed as close as possible to the source.
- Example syntax:
``` access-list 100 permit ip host 192.168.1.11 host 192.168.3.100 ```
```access-list 100 deny ip any host 192.168.3.100 ```

### 🏷️ Lab 31 – Named ACLs (ACLs Part 3)
**Objective:** Configure named ACLs to block communication between 192.168.1.0/24 and 192.168.2.0/24, while allowing all other traffic.
**Result:** Successfully denied traffic between the two LANs while keeping server access intact.
**Key Steps:**
- Create a named ACL using:
```ip access-list standard BLOCK_LAN```
```deny 192.168.2.0 0.0.0.255```
```permit any```
- Apply ACL to outbound traffic on R1 and R2.
- Verify that inter-LAN communication is blocked but other routes work.

**⚠️ Notes:**
- Named ACLs improve readability and management.
- Functionality is the same as numbered ACLs but easier to troubleshoot.

## 🔧 Skills Practiced
- Configuring standard ACLs to filter traffic based on source addresses.
- Implementing extended ACLs for fine-grained filtering (source, destination, and protocol).
- Using wildcard masks to define host or subnet rules.
- Applying named ACLs for easier readability and management.
- Determining correct placement of ACLs (close to source for extended, close to destination for standard).
- Verifying ACLs using show access-lists and connectivity tests (ping, tracert).

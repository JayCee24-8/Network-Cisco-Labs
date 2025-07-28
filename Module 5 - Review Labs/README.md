# 📘 Module 05 – Review Labs

This module reviews key networking concepts, combining VLANs, trunking, Router-on-a-Stick, and port security. The goal is to apply all the learned configurations and troubleshoot issues to achieve full network connectivity.

## 🧪 Labs Included

### 🔄 Lab 20 – Review Configuration Lab 1
**Objective:** Configure VLANs, trunk links, port security, and Router-on-a-Stick on a router.  
**Result:** Successfully set up VLAN13 and VLAN24, enabled sticky MAC learning, and verified inter-VLAN communication.  

**⚠️ Notes:**
- When configuring switch ports, ensure `switchport mode access` is applied before assigning the VLAN.  
- If you get stuck with *"Translating… domain server (255.255.255.255)"*, use **Ctrl+Shift+6** to cancel.  
- The router subinterface will only work if SW1's G0/1 interface is set to trunk mode, because trunking allows VLAN tagging.

### 🛠️ Lab 21 – Review Troubleshooting Lab 1
**Objective:** Find and fix misconfigurations on switches and routers.  
**Result:** Resolved issues with VLAN assignments, trunk mode, subinterface settings, and port security, restoring communication between all devices.

**⚠️ Notes:**
- Troubleshooting involves checking:  
  - Switch interfaces and VLAN assignments.  
  - Port security misconfigurations (e.g., wrong MAC address).  
  - Router subinterfaces (`show ip interface` to confirm VLAN IDs).  
- Remove incorrect secure MAC entries using `no switchport port-security mac-address [mac-address]`.  
- Ensure trunk links are active and set with `switchport mode trunk`.

## 🔧 Skills Practiced
- Creating and assigning VLANs  
- Configuring trunk ports  
- Setting up Router-on-a-Stick using subinterfaces  
- Enabling port security and sticky MAC addresses  
- Using `show` commands for troubleshooting  
- Testing connectivity with `ping`

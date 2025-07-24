# 📘 Module 04 – Port Security

This module explores port security on Cisco switches, focusing on controlling MAC address access, securing switch ports, and handling security violations. These labs follow Jeremy’s IT Lab Free CCNA Labs and provide hands-on experience with static and sticky MAC addresses as well as port violation modes.

## 🧪 Labs Included

### 🔐 Lab 17 – Port Security (Part 1)  
**Objective:** Enable port security, manually configure secure MAC addresses, and test violation scenarios.  
**Result:** Verified that the switch learns MAC addresses dynamically after traffic generation and enforces security by limiting allowed MACs.

### 🔐 Lab 18 – Port Security (Part 2)  
**Objective:** Configure and test sticky MAC address learning to persist secure MACs across reboots.  
**Result:** Confirmed that sticky MACs are saved in the running configuration and remain active even after a reload.

### 🔐 Lab 19 – Port Security (Part 3)  
**Objective:** Test port security violations caused by connecting unauthorized devices and reconfiguring interfaces.  
**Result:** Observed how the default violation action (shutdown) disables the interface, requiring manual recovery with `shutdown` and `no shutdown`.

## 🔧 Skills Practiced Across Labs
- Enabling and configuring port security on switch access ports.
- Setting static secure MAC addresses.
- Configuring sticky MAC address learning.
- Understanding and testing port violation modes (shutdown, restrict, protect).
- Recovering error-disabled ports due to security violations.
- Verifying secure MAC addresses using `show mac address-table` and `show running-config`.


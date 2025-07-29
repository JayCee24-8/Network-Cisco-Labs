# Module 06 – Remote Management (Telnet & SSH)

This module covers the configuration of remote access methods—Telnet and SSH—on Cisco devices. It highlights the differences in security between Telnet and SSH and includes key steps such as user account creation, VTY line configuration, and RSA key generation.

## 🧪 Labs Included

### 🔌 Lab 22 – Telnet
**Objective:**  
Configure Telnet remote access on a router and switch using local authentication.

**Key Steps:**
- Configured R1’s G0/0 and SW1’s VLAN1 interfaces with proper IP addressing.  
  **Note:** Interfaces must be brought up using `no shutdown`.
- Created a local user account with:  
  `username cisco password CCNA`
- Configured VTY lines (0–15) to use local login and only allow Telnet:  
`line vty 0 15
login local
transport input telnet`
- Successfully connected to devices from PC1 using:  
`telnet [device-ip]`

### 🔐 Lab 23 – SSH
**Objective:**  
Configure SSH remote access for secure encrypted connections.

**Key Steps:**
- Configured hostnames and IPs on R1 and SW1.
- Created a local user account:  
`username cisco password CCNA`
- **Warning:** Configured a DNS domain name:  
`ip domain-name cisco.com`  
This is required to generate RSA keys because SSH uses both the hostname and domain name.
- Generated RSA keys (1024 bits):  
`crypto key generate rsa`
- Configured VTY lines (0–15) to only allow SSH:  
`line vty 0 15
login local
transport input ssh
exec-timeout 5`
- Enabled SSH version 2:  
`ip ssh version 2`
- Successfully connected from PC1 using:  
`ssh -l cisco [ip-address]`  
**Note:** Unlike Telnet, the username must be specified with `-l`.

## 🔧 Skills Practiced
- Local user account creation for device authentication.
- Configuring VTY lines for Telnet and SSH access.
- Generating RSA keys for SSH encryption.
- Understanding why DNS domain names are required for SSH.
- Secure remote login testing from end devices.
- Applying timeout and privilege restrictions for remote access.

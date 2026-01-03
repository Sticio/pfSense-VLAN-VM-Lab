# pfSense Multi-VLAN Network Lab

## Overview
Built a virtualized network environment with segmented VLANs to demonstrate enterprise network architecture and security principles.

## What I Built

```
            Internet (NAT)
                 |
            [pfSense Firewall]
                 |
         ┌───────┴───────┐
      VLAN 10          VLAN 20
   (10.10.10.0/24)  (10.20.20.0/24)
         |               |
    Ubuntu VM        Xubuntu VM
```

## Technical Implementation

**Network Segmentation:**
- Created two isolated VLANs (VLAN 10 and VLAN 20) using IEEE 802.1Q tagging
- Configured pfSense as the central router/firewall managing all traffic
- Each VLAN has its own subnet and DHCP server

**Key Components:**
- **Hypervisor:** VirtualBox
- **Firewall:** pfSense 2.8.1
- **VLANs:** 
  - VLAN 10 (10.10.10.0/24) - Workstation network
  - VLAN 20 (10.20.20.0/24) - Server network
- **Clients:** Ubuntu and Xubuntu VMs with VLAN tagging configured

**What It Does:**
- Traffic isolation between VLANs
- Inter-VLAN routing controlled by firewall rules
- Both VLANs have internet access through NAT
- Demonstrates network segmentation security practices

## Testing & Validation

Successfully tested:
- ✅ DHCP assignment on both VLANs
- ✅ Internet connectivity from both VLANs
- ✅ Inter-VLAN communication (VLAN 10 ↔ VLAN 20)
- ✅ Firewall rule enforcement

![Inter-VLAN Connectivity Test](inter-vlan-test.png)
*Successful ping between VLAN 10 (10.10.10.100) and VLAN 20 (10.20.20.100)*

## Skills Demonstrated

- VLAN configuration and 802.1Q tagging
- Network segmentation architecture
- Firewall configuration and policy management
- Inter-VLAN routing
- Subnet planning and IP addressing
- Linux network interface configuration
- Virtualization and lab environment setup

## Why This Matters

This lab replicates how enterprises segment their networks for security and organization. By isolating workstations, servers, and other resources into separate VLANs, organizations can:
- Limit lateral movement in case of security breach
- Control traffic flow between network segments
- Improve network performance by reducing broadcast domains
- Implement granular access policies

---

**Technologies:** pfSense, VirtualBox, VLANs, Linux, Networking

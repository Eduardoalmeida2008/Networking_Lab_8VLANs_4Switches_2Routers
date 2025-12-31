# Networking_Lab_8VLANs_4Switches_2Routers
Collection of advanced networking labs with multiple VLANs, routers, and switches, all configured with DHCP, documenting topology, configuration, and connectivity tests. Labs created for hands-on practive and portfolio development.

# Networking Lab – December 2025

## Lab Overview
This lab is designed to **practice VLAN configuration, DHCP, inter-VLAN routing, and connectivity testing**.  
It includes **2 routers, 4 switches, and 8 VLANs**, with **3 PCs per VLAN**, all configured with DHCP.

---

## Topology Diagram
Include the topology diagram image here:  

`Topology.png`  

Quick description:  
- R1 connects VLANs 10 to 40  
- R2 connects VLANs 50 to 80  
- Switches distributed according to VLAN groups  
- PCs connected to their respective VLANs  

---

## Devices & Configuration

### Switches
- Switch1 – VLAN10, VLAN20  
- Switch2 – VLAN30, VLAN40  
- Switch3 – VLAN50, VLAN60  
- Switch4 – VLAN70, VLAN80  

### Routers
- R1 – Subinterfaces for VLANs 10 to 40  
- R2 – Subinterfaces for VLANs 50 to 80  
- Point-to-point link R1 ↔ R2: 192.168.100.0/30  

### PCs
- Each VLAN has 3 PCs, named as `VLAN10-1`, `VLAN10-2`, etc.  

---

## DHCP Configuration
All PCs receive IP addresses via DHCP:  

- VLAN10-40 → R1  
- VLAN50-80 → R2  

Prints:  
- `DHCP_VLAN10-40.png`  
- `DHCP_VLAN50-80.png`  

---

## Connectivity Tests
Ping tests to validate inter-VLAN communication:  

- `Ping_VLAN10_to_VLAN50.png`  
- `Ping_VLAN20_to_VLAN60.png`  
- `Ping_VLAN30_to_VLAN70.png`  
- `Ping_VLAN40_to_VLAN80.png`  

---

## Commands Used
- VLAN Configuration:
  ```bash
  vlan 10
  name VLAN10

Router Subinterfaces Configuration:

interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0


DHCP Configuration:

ip dhcp pool VLAN10
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1


Connectivity Tests:

ping <IP>

Notes

Lab created to consolidate VLAN setup, inter-VLAN routing, and DHCP configuration skills.

All devices configured using Packet Tracer or GNS3, depending on the environment.

Documentation is organized for easy replication and future review.

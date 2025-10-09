# Designing Resilient Networks: A Lab in High Availability, Routing, and Wireless Integration

# Executive Summary
 This infrastructure was designed to simulate a small business office network environment designed for **high availability, dynamic routing, logical segmentation, and hybrid connectivity**. 
I built it from the ground up in Cisco Packet Tracer, configuring routers, switches, DHCP, routing protocols, VLAN segmentation, and wireless access. 
The topology includes redundancy, dynamic routing, IP address management, and logical traffic separation 
and demonstrates the practical use of real-world protocols including **BGP**, **OSPF**, **HSRP**, **DHCP**, **VLANs**, and **WiFi security**,
configured and validated end-to-end.

# Project Purpose
I built this lab to showcase my ability to design and implement **resilient, production-grade network infrastructure**. 
This includes everything from protocol configuration to failure simulation and multi-layer validation.

# Key Skills Demonstrated
- Redundancy using HSRP for fault-tolerant gateways
- OSPF dynamic routing within an internal network
- BGP peering between autonomous systems to simulate WAN failover
- VLAN segmentation for wired/wireless isolation
- Centralized DHCP with multiple pools and default gateway routing
- Wireless Access Point configuration with WPA2 security
- Realistic end-user scenarios: PC + WiFi laptop testing
- Live CLI validation and troubleshooting


# Topology Diagram
[Topology Diagrams (PDF)](Diagrams/Topology Diagram.pdf)


# Repository Structure


# Technologies & Protocols Used

| Layer      | Protocol / Tool      | Purpose                               |
|------------|----------------------|----------------------------------------|
| Layer 2    | VLANs                | Segment wired and wireless traffic     |
| Layer 2/3  | HSRP                 | Gateway redundancy for failover        |
| Layer 3    | OSPF                 | Internal dynamic routing               |
| Layer 3    | BGP                  | External routing simulation (AS65001 ↔ AS65002) |
| Layer 3    | DHCP                 | Dynamic IP assignment for VLANs        |
| Wireless   | WPA2                 | Secure WiFi for VLAN 20 clients        |

[Rational of Protocols(PDF)](Protocols Used/Protocols_and_Rational.pdf)


# Devices in Topology
| Device   | Role                       | Notes                                  |
|----------|----------------------------|----------------------------------------|
| Router1  | Primary Gateway, DHCP, OSPF/BGP Peer | Active HSRP for VLANs 10 & 20        |
| Router2  | Backup Gateway, OSPF/BGP Peer       | Standby HSRP, BGP in AS 65002         |
| Switch1  | Layer 2 VLAN Switching     | Trunked to Router1                     |
| Switch2  | Layer 2 VLAN Switching     | Trunked to Router2                     |
| WAP      | WiFi Access Point          | VLAN 20, WPA2 secured                  |
| PC1/PC2  | DHCP Clients (Wired)       | Assigned from VLAN 10 DHCP pool        |
| Laptop   | WiFi Client (Wireless)     | Assigned from VLAN 20 DHCP pool        |


# Testing & Verification
Each component was tested using Packet Tracer CLI tools and device prompts:
- `show ip interface brief` (Router1, Router2)
- `show standby brief` (Router1, Router2)
- `show ip ospf neighbor` (Both routers)
- `show ip bgp summary` (Router1 or 2)
- `show vlan brief` (Switches)
- `show interfaces trunk` (Switches)
- `ipconfig` on PC1, PC2
- Ping tests from clients to default gateways and across VLANs

[Testing and My Approach(PDF)](Testing_and_Rational/Testing_and_Rational.pdf)


# Project Documentation
- [Configurations (Switches & Routers (PDFs](configs) 
- [Walkthrough Video(Youtube)](https://www.youtube.com/watch?v=hxoq7zfcVPU)
- [Command Line Outputs](Designing-Resilient-Networks
/CLI Outputs/)

# Let's Connect
Created by JD Wright  
https://www.linkedin.com/in/jeremidaviswright/  

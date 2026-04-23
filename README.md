
# Lab 01 - Segmented Office Network

### Project File 
[Download Packet Tracer File](Segmented-Office-Network/CPT-Project.pkt)

## What I Built
A segmented office network with three departments, each isolated in their own VLAN, 
with controlled inter-department access enforced by ACLs.

## Network Design
Base address space: 192.168.10.0/24 — subnetted into 3 zones:

| VLAN | Department | Subnet | Hosts |
|------|------------|--------|-------|
| 10 | Admin | 192.168.10.0/26 | 64 |
| 20 | Dev | 192.168.10.64/26 | 64 |
| 30 | Guest | 192.168.10.128/26 | 64 |

## What I Configured
- VLANs on all access switches
- Inter-VLAN routing using SVIs on a Layer 3 switch
- ACLs to enforce access policy:
  - Guest (VLAN 30) → cannot reach Admin (VLAN 10)
  - Dev (VLAN 20) → can reach both Admin and Guest
- Verified with ping tests between all VLANs

## Security Logic
The ACL mimics real-world network segmentation — 
untrusted users (Guest) are blocked from sensitive 
resources (Admin) at the network layer, not just 
the application layer.

## Tools Used
- Cisco Packet Tracer
- Subnetting: manual calculation (/26 from /24)

## Topology


![Network Topology](Segmented-Office-Network/screenshots/Network-Layout.png)



## Ping Tests


![Dev to Admin](Segmented-Office-Network/screenshots/ACLs-in-work.png)




![Guest blocked](Segmented-Office-Network/screenshots/ACLs-in-work.png)
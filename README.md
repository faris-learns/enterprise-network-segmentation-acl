# Enterprise Network Segmentation with VLANs & ACLs

## 📌 Overview
This project demonstrates enterprise-style network segmentation using VLANs, router-on-a-stick inter-VLAN routing, and extended Access Control Lists (ACLs) to enforce security boundaries between departments.

The goal was to restrict lateral movement between VLANs while allowing controlled access based on role.

---

## 🏗️ Network Design
- **VLAN 10 – ADMIN**
- **VLAN 20 – EMPLOYEES**
- **VLAN 30 – GUEST**
- Inter-VLAN routing implemented using **Router-on-a-Stick**
- 802.1Q trunk between switch and router

---

## 🔐 Security Controls (ACL Policy)
| VLAN | Allowed | Blocked |
|-----|--------|--------|
| ADMIN | Access to all VLANs | None |
| EMPLOYEES | Own VLAN only | ADMIN VLAN |
| GUEST | Internet / own VLAN | ADMIN & EMPLOYEES |

Extended ACLs were applied inbound on router subinterfaces to enforce least-privilege access.

---

## 🧪 Verification
Connectivity was verified using ICMP ping tests from each VLAN:
- ADMIN can reach all gateways
- EMPLOYEES blocked from ADMIN
- GUEST isolated from internal networks

Screenshots and packet tracer files are included as proof.

---

## 🛠️ Technologies Used
- Cisco Packet Tracer
- VLANs & Trunking (802.1Q)
- Router-on-a-Stick
- Extended ACLs
- ICMP testing

---

## 📂 Repository Structure

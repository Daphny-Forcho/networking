# Lab 2 – DHCP, DNS & Single Switch Network

## Objective
Build a single-switch network in Cisco Packet Tracer that connects 5 office PCs and 4 web servers, with a DHCP server dynamically assigning addresses to the PCs and a DNS server resolving domain names to the correct web servers.

## Topology
- **Switch:** S1 (single Cisco switch)
- **Network:** 192.168.200.0 /24
- **PCs:** 5 (DHCP clients)
- **Servers:** DHCP, DNS, www.coffee.com, www.dunkin.com, www.starbucks.com, www.peets.com

---

## Switch Port Assignments

| Device | Switch Port |
|--------|------------|
| PC1 | fa0/1 |
| PC2 | fa0/2 |
| PC3 | fa0/3 |
| PC4 | fa0/4 |
| PC5 | fa0/5 |
| www.coffee.com | fa0/10 |
| www.dunkin.com | fa0/11 |
| www.starbucks.com | fa0/12 |
| www.peets.com | fa0/13 |
| DHCP Server | g0/1 |
| DNS Server | g0/2 |

---

## IP Address Assignments

All static devices use the 192.168.200.0/24 network. The first available host address is 192.168.200.1.

| Device | IP Address |
|--------|------------|
| DHCP Server | 192.168.200.1 |
| DNS Server | 192.168.200.2 |
| www.coffee.com | 192.168.200.6 |
| www.dunkin.com | 192.168.200.7 |
| www.starbucks.com | 192.168.200.8 |
| www.peets.com | 192.168.200.9 |
| PC1–PC5 | Assigned via DHCP (starting at 192.168.200.100) |

---

## DHCP Server Configuration

The DHCP server was configured with a pool named **serverPool**:

| Setting | Value |
|---------|-------|
| Pool Name | serverPool |
| Start Address | 192.168.200.100 |
| Subnet Mask | 255.255.255.0 |
| DNS Server | 192.168.200.2 |
| Max Clients | 15 |

All 5 PCs were set to DHCP client mode and successfully received addresses from the pool (192.168.200.100 through 192.168.200.104).

---

## DNS Server Configuration

The DNS server (192.168.200.2) was configured with A records mapping each domain to its server's IP address:

| Domain | IP Address |
|--------|------------|
| www.coffee.com | 192.168.200.6 |
| www.dunkin.com | 192.168.200.7 |
| www.starbucks.com | 192.168.200.8 |
| www.peets.com | 192.168.200.9 |

---

## Verification

- All 5 PCs received IP addresses dynamically via DHCP
- DNS resolved each domain name to the correct web server IP
- PCs could browse to each website by domain name through the web browser in Packet Tracer

---

## Project File

[`coffee_one_switch.pka`](./coffee_one_switch.pka) — open with Cisco Packet Tracer to view the completed topology.

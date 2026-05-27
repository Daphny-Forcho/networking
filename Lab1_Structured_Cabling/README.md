# Lab 1 – Structured Cabling

## Objective
Design and implement a structured cabling system for a corporate office environment using Cisco Packet Tracer's Physical mode. The lab simulates real-world cabling infrastructure including wall mounts, patch panels, switches, and end devices, and concludes with full IP connectivity verified by ping and web browser access.

## Environment
- **Tool:** Cisco Packet Tracer (Physical Mode)
- **Location:** Home City → Corporate Office → IDF (Intermediate Distribution Frame)
- **Scope:** 7 offices + 1 server room

---

## What I Did

### Physical Infrastructure Setup

Navigated to the Corporate Office in Physical mode and opened the IDF view. Inside each of the 7 offices and the server room, I added copper wall mounts, naming each one to match its office number (Wall Mount 1 through Wall Mount 7, plus Wall Mount Server Room).

In the IDF wire closet, I added a new rack and installed:
- A **copper patch panel** for all incoming runs
- Two **Cisco 2960 switches** — one named **OfficeSwitch** (for the 7 office PCs) and one named **SvrSwitch** (for the server)

### Cabling Runs

Ran copper straight-through cables from each wall mount's punch down port 1 back to the corresponding punch down on the patch panel:
- Wall Mount 1 → Patch Panel port 1
- Wall Mount 2 → Patch Panel port 2
- ... through Wall Mount 7 → Patch Panel port 7
- Wall Mount Server Room → Patch Panel port 24

Then connected each patch panel port to the appropriate switch:
- Patch Panel ports 1–7 → OfficeSwitch ports 1–7 (straight-through)
- Patch Panel port 24 → SvrSwitch port 24 (straight-through)

Back in Physical view, connected jack 1 of each office wall mount to the corresponding PC's FastEthernet port using copper straight-through cables.

Finally, connected the two switches together using a **copper crossover cable** from SvrSwitch G0/1 to OfficeSwitch G0/1.

---

### IP Addressing

Used the 10th Class A network: **10.0.0.0/8**. Assigned the first 7 usable addresses to the office PCs and the 10th address to the server.

| Device | IP Address |
|--------|------------|
| PC 1 | 10.0.0.1 |
| PC 2 | 10.0.0.2 |
| PC 3 | 10.0.0.3 |
| PC 4 | 10.0.0.4 |
| PC 5 | 10.0.0.5 |
| PC 6 | 10.0.0.6 |
| PC 7 | 10.0.0.7 |
| Server | 10.0.0.10 |

---

### Verification

- Pinged all 7 PCs from PC1 — all pings successful
- Opened a web browser on one of the office PCs and navigated to `10.0.0.10` — successfully reached the server's web page
- Completed at **100% completion** in Packet Tracer

---

## Project File

[`structured_cabling.pka`](./structured_cabling.pka) — open with Cisco Packet Tracer to view the completed topology.

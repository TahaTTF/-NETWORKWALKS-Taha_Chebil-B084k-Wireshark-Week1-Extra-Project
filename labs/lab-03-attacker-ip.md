# Lab 3 — Identify the Attacker’s IP

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Identify the source of suspicious SYN probes, the target, probed ports, and the likely scan type.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Initial SYN probes; inspect sources, destinations and destination ports. |
| `tcp.flags.reset == 1` | RST responses, often associated with closed TCP ports. |
| `tcp.flags.syn == 1 && tcp.flags.ack == 1` | SYN/ACK responses, often associated with open TCP ports. |
| `ip.src == X.X.X.X` | Focus on a suspected source IP; replace placeholder. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Statistics → Conversations → TCP / IPv4 to identify frequent communicators
- Packet List: Source, Destination, Protocol, Info
- Packet Details → Transmission Control Protocol → Flags, Source Port, Destination Port

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

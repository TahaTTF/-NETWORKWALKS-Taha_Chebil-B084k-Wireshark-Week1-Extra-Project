# Lab 4 — Follow TCP Stream

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Reconstruct a chat conversation and locate details transmitted within a TCP connection.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `tcp` | Find TCP conversations. |
| `tcp.stream == N` | Isolate one TCP stream; replace N with the observed stream index. |
| `tcp.port == N` | Focus on the chat service port identified in the capture. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Right-click a relevant TCP packet → Follow → TCP Stream
- Follow TCP Stream window: conversation text, direction colors, stream selector
- Packet Details → TCP → Stream index; Statistics → Conversations → TCP

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

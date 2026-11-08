# Lab 8 — VoIP Call Replay

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Investigate a VoIP call, distinguish call signaling from voice media, and identify information exposed in a lab recording.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `sip` | Show Session Initiation Protocol signaling. |
| `rtp` | Show Real-time Transport Protocol packets, when Wireshark decodes them. |
| `sip.Method == "INVITE"` | Find SIP INVITE requests. |
| `sip.Status-Code == 200` | Find SIP 200 OK responses. |
| `udp` | Show UDP traffic, often used for VoIP signaling and media. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Telephony → VoIP Calls → select call → Flow Sequence / Play Streams (as available)
- Telephony → RTP → RTP Streams → Analyze / Player
- Packet Details → Session Initiation Protocol → From, To, Contact, Call-ID
- Packet Details → Session Description Protocol (SDP) → media ports and codecs

## Mistakes to avoid / troubleshooting notes
- SIP sets up and manages calls; RTP carries the audio packets.
- PCMU (G.711 μ-law) is an audio codec; it is not an encryption protocol.
- SRTP encrypts/authenticates media; ordinary RTP does not provide that protection.

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

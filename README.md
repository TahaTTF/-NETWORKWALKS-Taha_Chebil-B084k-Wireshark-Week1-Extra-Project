# Wireshark SOC Project — Week 1 Extra Labs

![Status](https://img.shields.io/badge/SOC_Labs-6%2F6_successful-brightgreen) ![Basic Quiz](https://img.shields.io/badge/Basic_Quiz-100%25-brightgreen) ![Advanced Quiz](https://img.shields.io/badge/Advanced_Quiz-80%25-blue)

**Participant:** Taha Chebil  
**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084  
**Project:** Week 1 Extra Project — Wireshark SOC / Packet Analysis  
**Completed:** 8 November 2026  
**Repository:** https://github.com/TahaTTF/-NETWORKWALKS-Taha_Chebil-B084k-Wireshark-Week1-Extra-Project

## Overview
This repository documents my practical Wireshark learning after completing the mandatory Week 1 Kali Linux / VirtualBox lab setup. I investigated provided packet captures, answered investigation questions, and completed six SOC labs and two quizzes.

The purpose is to document **what I learned, the Wireshark filters and tools I practiced, the difficult analysis steps, and important security observations**. The lab notes are study guides rather than exact packet-by-packet answer keys.

## Results

| Assessment | Topic | Result |
|---|---|---|
| Lab 3 | Identify the Attacker's IP | **100/100** |
| Lab 4 | Follow TCP Stream | **100/100** |
| Lab 5 | Follow TCP Stream, Part 2 | **100/100** |
| Lab 6 | HTTP Plain Text Credentials | **100/100** |
| Lab 7 | Brute Force Catch | **100/100** |
| Lab 8 | VoIP Call Replay | **100/100** |
| Wireshark Quiz | Basic | **100% (10/10)** |
| Wireshark Quiz | Advanced | **80% (8/10)** |

## Lab documentation

| Lab | Notes | Main technique |
|---|---|---|
| 3 | [Identify the Attacker's IP](labs/lab-03-attacker-ip.md) | SYN scan and TCP flag analysis |
| 4 | [Follow TCP Stream](labs/lab-04-follow-tcp-stream.md) | Reconstruct TCP chat |
| 5 | [Follow TCP Stream, Part 2](labs/lab-05-follow-tcp-stream-part-2.md) | HTTP investigation and stream correlation |
| 6 | [HTTP Plain Text Credentials](labs/lab-06-http-credentials.md) | Inspect unencrypted HTTP forms |
| 7 | [Brute Force Catch](labs/lab-07-brute-force.md) | Detect repeated authentication attempts |
| 8 | [VoIP Call Replay](labs/lab-08-voip-call-replay.md) | SIP signaling, RTP media and codecs |

## Key concepts and skills
- **Packet analysis:** source/destination IPs, ports, protocols, TCP flags and timestamps.
- **Wireshark display filters:** narrow visible packets without deleting captured data.
- **Follow TCP Stream:** reconstruct a conversation from multiple packets.
- **HTTP security:** understand exposure of credentials on unencrypted connections.
- **Brute-force investigation:** compare repeated login attempts and response evidence.
- **VoIP analysis:** distinguish SIP signaling, RTP media, codecs and encrypted SRTP.

## Quick filter reference

| Display filter | Purpose |
|---|---|
| `tcp` | TCP traffic |
| `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Initial SYN packets |
| `tcp.flags.reset == 1` | TCP resets |
| `tcp.stream == N` | One TCP conversation (replace N) |
| `http` | HTTP traffic |
| `http.request.method == "POST"` | HTTP POST requests |
| `http.response.code == 401` | HTTP Unauthorized responses |
| `sip` | SIP call signaling |
| `rtp` | RTP voice/media traffic |
| `ip.addr == X.X.X.X` | Packets to or from an IP (replace placeholder) |

**Note:** These are reusable reference filters, not a claim that each was entered during the labs. Capture filters and display filters have different syntax.

## Investigation workflow
1. Open the provided `.pcap` / `.pcapng` in Wireshark.
2. Identify the protocols and main hosts (`Statistics → Protocol Hierarchy`, `Statistics → Conversations`).
3. Apply a relevant **display filter**.
4. Examine packet metadata and protocol fields in **Packet Details**.
5. Reconstruct conversations with **Follow TCP Stream**, or inspect VoIP under **Telephony**.
6. Correlate multiple packets before drawing conclusions.
7. Record findings without exposing private or sensitive data.

## Challenges and lessons learned
The hardest *types of tasks* were distinguishing an attacker from a target, locating the correct TCP stream, correlating requests and responses, recognizing brute-force patterns, and mapping SIP calls to RTP media. These are investigation challenges; **I am not claiming that I personally made every mistake described in the lab notes**. The supplied screenshots show successful completion, not detailed error logs.

## Evidence / screenshots

Suggested filenames to upload to the `screenshots/` folder:

```text
screenshots/
  lab-03-score.png
  lab-04-score.png
  lab-05-score.png
  lab-06-score.png
  lab-07-score.png
  lab-08-score.png
  quiz-basic-score.png
  quiz-advanced-score.png
  week1-summary.png
```

Upload your original score images using these names (or update the paths to match your chosen names). No screenshots are bundled in this documentation package.

## Security and ethics
All analysis is based on authorized training exercises. Do not publish actual passwords, card details, confidential chat messages, sensitive packet captures, or recordings without authorization. Treat exported files as untrusted.

## Acknowledgments
Thanks to **Waqas Karim (CCIE)** and the **NetworkWalks** team for the training and practical exercises.

## Next steps
- Add the six score screenshots and two quiz results.
- Add a short note on any *real* mistakes or error messages from personal lab notes.
- Keep the documentation updated as I progress through the internship.

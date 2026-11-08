# Lab 7 — Brute Force Catch

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Detect repeated failed logins followed by a successful login in a training capture.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `http.request.method == "POST"` | Identify candidate HTTP login submissions. |
| `http.response.code == 401` | Find HTTP Unauthorized responses, if the application uses 401. |
| `http.response.code == 200` | Find successful HTTP responses; not necessarily a successful login. |
| `tcp.stream == N` | Correlate a request with its response in a specific stream. |
| `ip.src == X.X.X.X && http.request` | Narrow requests from a suspected source. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Packet List: compare repeated requests over time
- Packet Details → HTTP response status and application response body
- Statistics → Conversations → IPv4/TCP; Follow TCP Stream

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

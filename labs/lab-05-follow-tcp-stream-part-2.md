# Lab 5 — Follow TCP Stream, Part 2

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Inspect web traffic and reconstructed streams to locate a code word, backup server, report details, and a downloaded file.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `http` | Show decoded HTTP messages. |
| `http.request` | Find HTTP requests. |
| `http.response` | Find HTTP responses. |
| `http.response.code == 200` | Find successful HTTP responses. |
| `tcp.stream == N` | Isolate the stream containing relevant content. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Packet List → HTTP request/response and Info columns
- Packet Details → Hypertext Transfer Protocol → Host, URI, Status Code
- Right-click packet → Follow → TCP Stream
- File → Export Objects → HTTP (when an object is available)

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

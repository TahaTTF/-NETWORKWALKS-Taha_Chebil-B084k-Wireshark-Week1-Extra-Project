# Lab 6 — HTTP Plain Text Credentials

**Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship  
**Batch:** B084 | **Participant:** Taha Chebil | **Result:** 100/100  
**Date:** 7 November 2026 (Labs 3–5) / 8 November 2026 (Labs 6–8) — see individual score screenshots for exact date.

## Objective
Inspect an unencrypted HTTP login request and understand why cleartext authentication is unsafe.

## What I learned
- How to investigate captured traffic using protocol fields and Wireshark display filters.
- How to connect evidence from packet lists, packet details, and reconstructed conversations.
- How to avoid conclusions based on a single packet without context.

## Useful Wireshark display filters

| Filter | Role / note |
|---|---|
| `http` | Show HTTP traffic. |
| `http.request.method == "POST"` | Show HTTP POST requests, commonly used for forms. |
| `http.request.uri contains "login"` | Search for login-related URLs (only if the URI contains that word). |
| `ip.src == X.X.X.X` | Focus on the PC submitting a request. |

> These are reusable study filters appropriate for the lab topic, **not a verified transcript of every filter I typed**. Replace placeholders with values from your own PCAP.

## Where I found the answers
- Packet List → HTTP POST request
- Packet Details → Hypertext Transfer Protocol → HTML Form URL Encoded (when decoded)
- Right-click → Follow → HTTP Stream or TCP Stream

## Result and evidence
- **Score:** 100/100 (all 10 tasks correct).

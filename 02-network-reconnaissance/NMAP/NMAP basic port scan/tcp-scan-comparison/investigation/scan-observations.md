# Scan observations

Observations from the accompanying scan screenshots.

| Capture | Visible command | Observed result |
| --- | --- | --- |
| Earlier, 18:09 UTC | `nmap -sF 10.64.159.173` | Nine listed ports open\|filtered; 991 closed (reset). |
| Earlier, 18:09 UTC | `nmap -sN 10.64.159.173` | Nine listed ports open\|filtered; 991 closed (reset). |
| Earlier, 18:09 UTC | `nmap -sT 10.64.159.173` | Nine listed ports open; 991 closed (conn-refused). |
| Later, 18:11 UTC | `nmap -sT -p 1-1000 10.64.159.173` | 22, 25, 80 open; 443 closed; 986 filtered (no-response) and 10 filtered (host-unreach). |
| Later, 18:12 UTC | `nmap -sN -p 1-1000,5000 10.64.159.173` | All 1001 scanned ports open\|filtered (no-response). |
| Later, 18:12 UTC | `nmap -sN 10.64.159.173` | All 1000 scanned ports open\|filtered (no-response). |
| Later, 18:13 UTC | `nmap -sF 10.64.159.173` | All 1000 scanned ports open\|filtered (no-response). |

All times above come from 7 August 2026 terminal output. The earlier scan and later scoped scan are not controlled equivalents: time and port scope differ. No change to a firewall or target configuration is demonstrated. The label `open|filtered` must not be shortened to `open`.

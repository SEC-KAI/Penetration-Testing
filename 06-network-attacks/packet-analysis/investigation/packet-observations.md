# Packet observations

Source: `../screenshots/01-icmp-tcp-fragment-observation.png`. Analysis is limited to the packet fields visible in the screenshot.

| Frame(s) | Visible fields | Interpretation |
| --- | --- | --- |
| 796 / 807 | Echo request 10.10.166.81 → 10.201.89.221; reply in reverse direction | The target responds to this ICMP exchange. |
| 805 / 806 | ICMP timestamp request / reply | Another visible host response. |
| 799 | TCP 62334 → 443, SYN | A SYN probe is displayed; the crop does not show a completed connection. |
| 802 | TCP 62334 → 80, ACK | An ACK probe is displayed; it is not itself a server acknowledgment. |
| 797 / 798 | IPv4 fragments, ID 7ac7, offsets 0 and 8 | Fragmentation is visible; full reassembly requires the original capture. |
| 808–810 | Fragments followed by TCP 62590 → 80, SYN | Wireshark displays a reassembled protocol interpretation. |

The screenshot is insufficient to attribute an exact Nmap command, prove evasion or establish MITM. The targets are separate from the Kali/Windows ARP lab.

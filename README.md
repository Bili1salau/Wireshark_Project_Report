# Wireshark_Project_Report
Wireshark Project Report TCP-3-Way Handshake &amp; Stealth Scan
# Wireshark Project Report — TCP 3-Way Handshake & Stealth/Decoy Scan Analysis

## Summary

This report documents a Wireshark analysis of a TCP three-way handshake between the host **192.168.1.4** and the server **66.29.153.49** on port **80**. The packet capture was filtered by IP address and TCP port to isolate the session. In addition to the handshake analysis, the report examines stealth scanning techniques — including SYN (stealth) scans, decoy scans, and time-fragmentation scans — describes how these methods can evade detection, and provides recommended approaches for detecting and mitigating them.

## Methodology

* The capture was narrowed using IP and TCP port filters to concentrate on the session of interest (192.168.1.3 ⇄ 66.29.153.49:80).
* Packet-level inspection in Wireshark was used to follow the TCP stream and verify sequence/acknowledgement behavior during the handshake.
* Common stealth scanning techniques were simulated and analyzed to show their observable network artifacts and evasion characteristics.

## Findings

* The TCP three-way handshake (SYN → SYN/ACK → ACK) between 192.168.1.3 and 66.29.153.49 on port 80 was successfully identified and reconstructed from the filtered capture.
* SYN (stealth) scans can minimize stateful connection establishment by sending SYNs and interpreting replies without completing full connections, making them harder to detect in some logging setups.
* Decoy scans mix probe traffic from multiple source IPs to obscure the true scanner and complicate attribution.
* Time-fragmentation scans spread scan packets over long time intervals or fragment packets to evade signature-based detection and threshold triggers.

## Recommendations

* Use combined detection approaches: correlate flow data, firewall logs, and IDS/IPS alerts rather than relying on a single source.
* Implement anomaly-based detection and rate/threshold monitoring to spot irregular SYN rates or unusual inter-arrival timing.
* Harden logging and enable full packet capture for suspicious flows to allow retrospective analysis.
* Employ ingress/egress filtering and source address validation to reduce the effectiveness of spoofed decoy traffic.
* Keep IDS/IPS signatures updated and tune sensitivity to catch fragmented or low-and-slow scans.


If you want, I can tailor this rewrite to a specific audience (technical lab report, executives and Wireshark screenshots. Which format would you like next?

(https://github.com/Bili1salau/Wireshark_Project_Report/blob/main/Wireshark_Project_Report.pdf)

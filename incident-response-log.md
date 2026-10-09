# Incident Response Simulation — SYN Flood

## Detection
Command used to generate traffic:
sudo hping3 -S --flood -V -p 80 192.168.56.102

Wireshark (live capture on host-only interface eth0) showed:
- 93,000+ TCP packets captured in a short window
- Source: 192.168.56.101 (Kali) → Destination: 192.168.56.102 (Metasploitable2), port 80
- Pattern: rapid-fire SYN packets, each immediately answered with RST,ACK
- No completed TCP handshakes — classic SYN flood signature

## Containment
sudo iptables -A INPUT -s 192.168.56.101 -p tcp --dport 80 -j DROP
→ Blocks further inbound traffic from the attacking source IP to the web service

## Eradication & Recovery
- Verified flood stopped via a fresh, clean Wireshark capture
- Reviewed firewall rule scope (source-IP specific, not overly broad)
- Recommended patching/hardening the targeted service rather than relying on
  blocking alone

## Post-Incident Summary
Incident: SYN flood DoS attempt against 192.168.56.102:80, from 192.168.56.101.
Detected: Wireshark packet-rate/volume anomaly.
Contained: Source-IP iptables DROP rule.
Impact: None (controlled lab simulation).
Recommendation: Automate detection/blocking via IDS/IPS in production environments.

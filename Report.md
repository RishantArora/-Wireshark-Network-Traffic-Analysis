# 📄 Wireshark Task Report

## ✅ Task Summary

1. **Installed Wireshark** on Windows.
2. **Captured traffic** using active interface (`wlan0`).
3. **Generated traffic** by browsing and pinging (`ping google.com`, opened example websites).
4. **Stopped capture** after about 1 minute.
5. **Used filters** like `http`, `dns`, `tcp`, `icmp`, `quic` to analyze traffic.
6. **Saved the session** as `Packet_analysis.pcap`.
7. **Analyzed the capture** using **Statistics → Protocol Hierarchy**.

---

## 📦 Protocols Identified (from Protocol Hierarchy)

| Protocol                | Packet Count | % of Total | Purpose |
|-------------------------|--------------|------------|---------|
| **QUIC (IETF)**         | 5582         | 80.0%      | Fast, encrypted web traffic (used by Google, YouTube, etc.) |
| **UDP**                 | 5869         | 81.5%      | Transport layer for QUIC and DNS |
| **TCP**                 | 1046         | 13.2%      | Traditional transport protocol |
| **TLS (Transport Layer Security)** | 449 | 6.4% | Encrypted HTTP (HTTPS) |
| **DNS**                 | 112          | 1.6%       | Domain name resolution |
| **ICMPv6**              | 34           | 0.5%       | IPv6 diagnostics |
| **HTTP**                | 2            | 0.03%      | Minimal unencrypted web traffic |
| **ARP**                 | 40           | 0.6%       | Address resolution in LAN |

---

## 🔍 Observations

- **QUIC was the dominant protocol**, likely due to Chrome-based services or Google apps.
- **Most web traffic was encrypted**, either via QUIC or TLS over TCP.
- **Minimal HTTP traffic**, showing the shift to modern secure communication.
- **DNS traffic** confirmed domain name lookups.
- **Local protocols** like ARP and ICMPv6 were also active, indicating LAN activity.

---

## 🧠 Key Learnings

- Encrypted protocols (QUIC, TLS) dominate modern internet traffic.
- DNS is a crucial early step in almost every internet request.
- Wireshark is powerful for seeing what’s happening beneath the surface.

---


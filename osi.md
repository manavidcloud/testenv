# OSI Model – Full Table Reference

| **Layer** | **Function** | **PDU (Data Unit)** | **Devices** | **Protocols / Examples** | **Sample Data / Headers** |
|-----------|--------------|---------------------|-------------|---------------------------|----------------------------|
| **7. Application** | Provides network services to end-user applications (browsers, email, file transfer, DNS lookups) | Data / Message | PCs, Phones, Servers | HTTP, HTTPS, FTP, SMTP, IMAP, DNS, DHCP, SNMP | `GET /index.html HTTP/1.1`<br>`Host: example.com` |
| **6. Presentation** | Data translation, encryption, compression | Data | Gateways, Proxies | SSL/TLS, MIME, JPEG, MPEG, PNG, ASCII | TLS Record → `Content Type, Version, Length` |
| **5. Session** | Establishes, manages, and terminates communication sessions (authentication, checkpoints, dialogs) | Data | Gateways, Application Servers | NetBIOS, RPC, SMB, SIP, PPTP | Session ID, Token Exchange |
| **4. Transport** | Reliable/unreliable delivery, segmentation, sequencing, error recovery, flow control | Segment (TCP)<br>Datagram (UDP) | Firewalls, Load Balancers | TCP, UDP, SCTP | **TCP Header:** SrcPort=54321, DstPort=80, Seq=1A2B3C, Ack=00000000, Flags=SYN |
| **3. Network** | Logical addressing, routing, path determination | Packet | Routers, Layer 3 Switches | IPv4, IPv6, ICMP, IPsec, OSPF, BGP, RIP | **IPv4 Header:** Version=4, TTL=64, SrcIP=192.0.2.10, DstIP=198.51.100.25 |
| **2. Data Link** | Framing, MAC addressing, error detection (CRC), flow control | Frame | Switches, Bridges, NICs | Ethernet (802.3), ARP, VLAN (802.1Q), Wi-Fi (802.11), PPP | **Ethernet Frame:** DestMAC=00:11:22:33:44:55, SrcMAC=66:77:88:99:AA:BB, Ethertype=0x0800, FCS=CRC32 |
| **1. Physical** | Transmits raw bits as electrical/optical/radio signals across physical medium | Bits (0s & 1s) | Hubs, Repeaters, Cables, Fiber, Modems | RS-232, DSL, Fiber Optics, Coaxial Cable, Ethernet Physical Layer | Example Transmission: `10110101` (NRZ/Manchester encoded, voltage/light pulses) |

---

# Quick Encapsulation Path

1. **Application (Layer 7):** HTTP GET request  
2. **Transport (Layer 4):** TCP Header (Ports, Seq, Ack, Flags) added  
3. **Network (Layer 3):** IP Header (SrcIP, DstIP, TTL, Protocol) added  
4. **Data Link (Layer 2):** Ethernet Frame (MAC addresses + FCS) added  
5. **Physical (Layer 1):** Encoded into bits → `10110101...` sent over cable/fiber/wireless

# Wireshark Protocol Analysis
1. Running 'Wireshark' from CLI
   ![Wireshark](screenshots/wireshark_run.png)
   
2. Capturing packets using Wireshark
   ![Wireshark Interface](screenshots/wireshark_interface.png)

3. Wireshark Protocol Hierarchy
   ![Protocol Hierarchy](screenshots/protocol.png)
Based on the packet capture from interface `eth0`, here is the protocol distribution:

- **Total Packets:** 5155
- **Top Protocols by Packet Count:**
  - Transmission Control Protocol (TCP): 88.5%
  - Transport Layer Security (TLS): 22.5%
  - QUIC, DNS, HTTP, ARP: Minor traces

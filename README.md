http-packet-tracer-lab
HTTP Communication Simulation (Packet Tracer)

📌 Objective

Understand how HTTP works at the Application Layer
Observe packet transmission between a client and a server
Analyze HTTP requests and responses using Simulation Mode

🖥️ Network Topology

Devices used:

1 PC
1 Server
1 Switch (2960)
1 Router (4331)

Connections:

PC → Switch
Server → Switch
Switch → Router

🌐 IP Addressing

| Device | Interface | IP Address   | Subnet Mask   | Default Gateway |
| ------ | --------- | ------------ | ------------- | --------------- |
| PC     | NIC       | 192.168.1.10 | 255.255.255.0 | 192.168.1.1     |
| Server | NIC       | 192.168.1.20 | 255.255.255.0 | 192.168.1.1     |
| Router | G0/0/0    | 192.168.1.1  | 255.255.255.0 | N/A             |

⚙️ Configuration Steps

1. Assign IP addresses to PC and Server
2. Configure router interface:

```
enable
configure terminal
interface gigabitethernet0/0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
write memory
```

3. Enable HTTP service on Server
4. Test connectivity using:

```
ping 192.168.1.20
```

5. Open browser on PC:

```
http://192.168.1.20
```

🔍 Simulation Observations

ARP

* PC sends ARP request to find server MAC address
* Server replies with its MAC address

TCP Handshake

* SYN → SYN-ACK → ACK establishes connection

HTTP

* Client sends GET request
* Server responds with 200 OK and webpage content

🧠 Key Takeaways

* HTTP operates at the Application Layer
* TCP ensures reliable communication
* ARP is required before communication begins
* Devices in the same network communicate through the switch (router not used)

📁 Files

* Packet Tracer file (.pkt)
* Screenshots of simulation mode (ARP, TCP, HTTP)

✅ Conclusion

This lab demonstrates how HTTP communication works across network layers and how data flows between a client and server in a LAN environment.

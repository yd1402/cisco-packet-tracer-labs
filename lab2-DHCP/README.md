# Lab 02 — DHCP Configuration

## Objective
Configured a router as a DHCP server in Cisco Packet Tracer to automatically assign IP addresses to client PCs.

---

## Network Topology

![Topology](topology-lab2.png)

![Topology](topology-lab2(2).png)

---

## Devices Used
- 1 Router (1941)
- 1 Switch (2960)
- 2 PCs

---

## Skills Practiced
- DHCP configuration
- Router configuration
- IP assignment
- Connectivity testing
- DORA process analysis
- MAC address learning

---

## Router Configuration

```bash
enable
configure terminal

interface gig0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
exit
```

---

## Commands Used

```bash
ipconfig
ping 192.168.1.1
show mac address-table
```

---

## DORA Process

![DORA Process](dora-process.png)

![DORA Process](dora-process(2).png)

![DORA Process](dora-process(3).png)

![DORA Process](dora-process(4).png)

![DORA Process](dora-process(5).png)

---

## Ping Test

![Ping Test](ping-test.png)

![Ping Test](ping-test(2).png)

![Ping Test](ping-test.(3)png)

![Ping Test](ping-test(4).png)

![Ping Test](ping-test(5).png)

![Ping Test](ping-test(6).png)

---

## MAC Address Table

![MAC Table](mac-addeess-table.png)

---

## Router Configuration

![Router Configuration](Router-Configuration.png)

![Router Configuration](Router-Configuration(2).png)

---

## What I Observed
- DHCP Discover packets were broadcast to all devices
- The switch forwarded DHCP traffic
- PCs automatically received IP addresses
- The DORA process was visible in simulation mode
- The switch dynamically learned MAC addresses

---

## Challenges Faced
- Initial DHCP packets failed before successful retries
- Learned the importance of enabling interfaces using `no shutdown`

---

## SOC Relevance
Understanding DHCP is important for SOC analysts because DHCP logs help identify devices, track IP assignments, and investigate suspicious network activity.

---

## Outcome
Successfully configured DHCP in Cisco Packet Tracer and verified connectivity between devices.

## Result

![Result](result.png)

---

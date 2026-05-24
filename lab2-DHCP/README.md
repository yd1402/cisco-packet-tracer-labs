# Lab 02 — DHCP Configuration

## Objective
The objective of this lab was to configure a router as a DHCP server in Cisco Packet Tracer and allow client PCs to automatically receive IP addresses.

---

## Network Topology

PC0 → Switch → Router  
PC1 → Switch → Router

---

## Devices Used
- 1 Router (1941)
- 1 Switch (2960)
- 2 PCs

---

## Skills Practiced
- DHCP configuration
- Router configuration
- IP address assignment
- Connectivity testing
- Packet flow analysis
- DORA process observation

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

## What I Observed
- DHCP Discover packets were broadcast across the network
- The switch forwarded DHCP traffic to connected devices
- PCs automatically received IP addresses from the router
- The DORA process was visible in simulation mode
- The switch learned MAC addresses dynamically

---

## Challenges Faced
- Initial DHCP packets failed before successful retries
- Learned the importance of enabling interfaces using `no shutdown`

---

## SOC Relevance
Understanding DHCP is important in SOC operations because analysts use DHCP logs to:
- identify devices on a network
- trace IP address assignments
- investigate suspicious systems
- analyze internal network activity

---

## Outcome
Successfully configured DHCP in Cisco Packet Tracer and verified connectivity between devices using ping.

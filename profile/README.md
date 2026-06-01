# Styx FLF

Web-based network management platform for Linux — firewall, routing, VPN, QoS, and eBPF from a
single control plane.

Note: This is a technology preview and should not be used in production environment
---

## Key Capabilities

### Firewall & NAT
Full nftables rule management across filter and NAT chains. 
Objects-based model

### Routing
Static routes with ECMP multipath, custom routing tables, metrics, and MTU. Dynamic routing
support for BGP, OSPF, RIP, BFD, and IGMP.

### IPsec VPN
IKEv1 and IKEv2 tunnel and transport mode. Site-to-site and remote access (road warrior)
topologies. Certificate and PSK authentication, virtual IP pools, DPD, and per-connection
crypto proposal negotiation. Full tunnel lifecycle control from the UI.

### Traffic Control
Support for most common qdisc with rate-limited classes and traffic classification filters. Real-time
interface traffic statistics.

### Packet Marking
Support for packet marking.

### eBPF (not yet implemented)
Attach, detach, and list kernel eBPF programs. Structured feedback system with per-module
statistics, events, and alerts surfaced in the dashboard.

### Monitoring & SLA
ICMP, DNS, and HTTP reachability monitors. Built-in iperf3 bandwidth testing. Real-time Charts.

### Security 
RBAC with role-based capabilities.
The solution incorporates auditing and monitoring mechanisms for both software and system.
AppArmor and auditd configuration. IDS/IPS rule management (not yet implemented)

### Detection
Basic host detection/events and topology

### API & Automation
REST API with token authentication. 
Full configuration management through the API — deploy and manage firewall rules, VPN tunnels, interfaces, 
routes, and QoS policies programmatically. No CLI scripting needed; everything the UI can do is available via
the API for integration with automation workflows and third-party tools.

### Platform
Configuration backup and restore. System event log with filtering and acknowledgement. Full
multi-user support with session and token-based auth.

---

## Architecture

Latest Linux Kernel technology. Zero build step, zero external dependencies — fully self-contained.

---


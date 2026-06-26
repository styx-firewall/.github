# Styx FLF

Web-based network management platform for Linux — firewall, routing, VPN, QoS, and eBPF from a
single control plane.

Note: This is a preview and should not be used in production environment

You can download the ISO from:
https://github.com/styx-firewall/styx-flf

---

# Key capability that will support

## Firewall & NAT (initial)
Full nftables rule management across filter and NAT chains. 
Objects-based model

## Routing (initial)
Static routes with ECMP multipath, custom routing tables, metrics, and MTU. 

### Dynamic Routing (draft)
Dynamic routing support for BGP, OSPF, RIP, BFD, IGMP.

## IPsec VPN (initial)
IKEv1 and IKEv2 tunnel and transport mode. Site-to-site and remote access (road warrior)
topologies. Full tunnel lifecycle control from the UI.

## Traffic Control (initial) 

### Packet marking support
Routing, TC,  and Firewall Packet Marking Support

### TC
Support for most common qdisc with rate-limited classes and traffic classification filters. Real-time
interface traffic statistics. 


## eBPF (concept)
Attach, detach, and list kernel eBPF programs. Structured feedback system with per-module
statistics, events, and alerts surfaced in the dashboard.

## Monitoring/Watchdog & SLA (initial)
ICMP, DNS, and HTTP reachability monitors. Built-in iperf3 bandwidth testing. Real-time Charts.
Internal Services Watchdogs

## Security

### RBAC with role-based capabilities. (initial)
The solution incorporates auditing and monitoring mechanisms for both software and system.
AppArmor and auditd configuration. IDS/IPS rule management (not yet implemented)

### Auditing (initial)
Internal auditing

### Auditd (pending)

### Detection (inital)
Basic host detection/events and network topology

### API & Automation (inital)
REST API with token authentication. 
Full configuration management through the API — deploy and manage firewall rules, VPN tunnels, interfaces, 
routes, and QoS policies programmatically. No CLI scripting needed; everything the UI can do is available via
the API for integration with automation workflows and third-party tools.

### Platform
Configuration backup and restore. System event log with filtering and acknowledgement. Full
multi-user support with session and token-based auth.

---

## Architecture

Latest Linux Kernel technology. Zero build step, Fully self-contained.

---


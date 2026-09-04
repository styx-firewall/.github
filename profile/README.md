# Styx FLF

A web-based network management platform for Linux that provides centralized management of firewall, routing, VPN, QoS, monitoring, and custom eBPF modules.

Download the latest preview ISO:

https://github.com/styx-firewall/styx-flf

> **Warning:** This is tech preview intended for testing only.

---

# Current/Planned Capabilities

## Networking *(testing)*

Configure physical and virtual interfaces


## Firewall & NAT *(testing)*

* Full nftables rule management across filter and NAT tables.
* Object-based configuration model.

## Routing *(testing)*

* Static routes.
* Multipath routing.
* Routing tables.

### Dynamic Routing *(testing)* *(partially testing)*

Support for:

* BGP *testing*
* OSPF *dev*
* RIP *dev*
* BFD *testing*
* IGMP proxy support *dev*

## IPsec VPN *(testing)*

* IKEv1 and IKEv2.
* Tunnel and transport modes.
* Site-to-site and remote access (road warrior).
* Complete tunnel lifecycle management from the web interface.

## Traffic Control *(testing)*

### Packet Marking *(testing)*

Packet marking support for:

* Routing
* Firewall
* Traffic Control (TC)

### QoS (*testing*)

* Support for the most commonly used qdiscs.
* Rate-limited classes.
* Traffic classification filters.
* Rules Interface
* 
### Dashboard & Statistics 

* Real-time monitoring charts and status.
* Real-time interface traffic statistics.

## eBPF *(testing)*
* CORE *testing* BCC *dev*
* Attach, detach, and manage kernel eBPF programs.
* Per-module statistics.
* Telemetry/Events and alerts integrated into the dashboard (Telemetry).

## Monitoring & SLA 

### Reachability Monitoring

* ICMP *

### Performance Testing *(testing)*

* iperf3 bandwidth testing.

### Watchdog

* Internal service watchdogs.

## Security

### Access Control *(testing)*

* Role-Based Access Control (RBAC).
* Fine-grained permissions.
* Multi-user support.

### System Hardening *(planned)*

* AppArmor configuration and policy management.

### Auditing *(testing)*

* Internal auditing.

### auditd *(planned)*

* auditd configuration and log management.

### Detection *(initial)*

* Basic host event detection.
* Basic Network topology discovery.
* Anomalies/services detection in networks *(planned)*

### IDS / IPS *(planned)*

* Suricata IDS/IPS support.

## API & Automation *(testing/draft)*

* REST API with token-based authentication.
* Complete configuration management through the API.
* Firewall, VPN, interfaces, routing, and QoS management.
* Every feature available in the web interface is also available through the API.
* NOTE: The current API is not the final version, it was developed as an initial interface to enable real-world internal testing of the software. A significant API redesign is planned for the future.

## Telemtry System *testing* *partially* 

The telemetry system is a **generic, subsystem-agnostic pub/sub pipeline** that collects, routes, stores, and exports operational data from any Styx component. While the initial producer is the eBPF subsystem, the pipeline is designed so that firewall, BGP, strongSwan, DHCP, discovery, and any future service can publish telemetry through the same bus without coupling.


## Platform

* Configuration backup and restore.
* Unified configuration model with distinct running and startup states.
* System/Networking logging and Telemtry bus (pub/sub)
* Session-based and token-based authentication.

---

# Architecture

* Built on the latest Linux kernel technologies.
* Debian Based


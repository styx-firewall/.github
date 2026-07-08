# Styx FLF

A web-based network management platform for Linux that provides centralized management of firewall, routing, VPN, QoS, monitoring, and eBPF from a single control plane.

> **Note:** This is an early preview and **must not** be used in production environments.

Download the latest preview ISO:

https://github.com/styx-firewall/styx-flf

> **Warning:** This is a very early preview intended for testing only.

---

# Planned Capabilities

## Firewall & NAT *(testing)*

* Full nftables rule management across filter and NAT tables.
* Object-based configuration model.

## Routing *(testing)*

* Static routes.
* Multipath routing.
* Routing tables.

### Dynamic Routing *(draft)*

Support for:

* BGP
* OSPF
* RIP
* BFD
* IGMP

## IPsec VPN *(initial)*

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

### Dashboard & Statistics 

* Real-time monitoring charts and status.
* Real-time interface traffic statistics.

## eBPF *(prototyping)*

* Attach, detach, and manage kernel eBPF programs.
* Per-module statistics.
* Events and alerts integrated into the dashboard.

## Monitoring & SLA 

### Reachability Monitoring

* ICMP *

### Performance Testing *(testing)*

* iperf3 bandwidth testing.

### Watchdog

* Internal service watchdogs.

## Security

### Access Control *(initial)*

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
* Network topology discovery.
* Anomalise/services detection in networks *(planned)*

### IDS / IPS *(planned)*

* Suricata IDS/IPS support.

## API & Automation *(draft)*

* REST API with token-based authentication.
* Complete configuration management through the API.
* Firewall, VPN, interfaces, routing, and QoS management.
* Every feature available in the web interface is also available through the API.

## Platform

* Configuration backup and restore.
* Unified configuration model with distinct running and startup states.
* System event log with filtering and acknowledgement.
* Session-based and token-based authentication.

---

# Architecture

* Built on the latest Linux kernel technologies.
* No build step required.
* Fully self-contained.

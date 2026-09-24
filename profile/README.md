# Styx FLF

A web-based network management platform for Linux that provides centralized management of firewall, routing, VPN, QoS, monitoring, and custom eBPF modules.

Download the latest preview ISO:

https://github.com/styx-firewall/styx-flf

> **Warning:** This is tech preview intended for testing only.
 
[Issues](https://github.com/styx-firewall/styx-flf/issues)

NOTE:  By default, the test branch is installed, which will be less up-to-date than the dev version. However, the dev version is updated more frequently and may break between updates. You can change the branch from the UI.

---

# Current and Planned Capabilities

The capabilities marked as dev is still under development and may have limited functionality or known issues, while the
other features are more advanced and should work but require further testing.


## Networking

Configure physical and virtual interfaces

* Physical Interfaces
* VLAN *(dev)*
* Bridge 
* MacVLAN
* Bond *(dev)*
* Loopback
* PPPoE *(dev)*
* VTI *(dev)*
* GRE *(dev)*
* VXLAN *(dev)*
* VRF *(dev)*
* XFRM *(dev)*

## Firewall & NAT *(testing)*
 
* Full nftables rule management across filter and NAT tables.
* Object-based configuration model.

## Routing & Dynamic Routing*

* Static routes.
* Multipath routing.
* Routing tables.
* BGP
* OSPF *(dev)*
* RIP  *(dev)*
* BFD
* IGMP proxy support *(dev)*

## IPsec VPN

* IKEv1 and IKEv2.
* Tunnel and transport modes.
* Site-to-site and remote access (road warrior).
* Complete tunnel lifecycle management from the web interface.

## Traffic Control 

### Packet Marking *(test)*

Packet marking support for:

* Routing
* Firewall
* Traffic Control (TC)

### TC/QoS

* Support for the most commonly used qdiscs.
* Rate-limited classes.
* Traffic classification filters.
* TC Rules

### Dashboard & Statistics 

* Real-time monitoring charts and status.
* Real-time interface traffic statistics.

## eBPF

* CORE support
* BCC *(dev)*
* Attach, detach, and manage kernel eBPF programs.
* Per-module statistics.
* Telemetry/Events and alerts integrated into the dashboard.

## Monitoring & SLA 

### SLA, Reachability, Monitoring

* ICMP

### Performance Testing

* iperf3 bandwidth testing.

### Watchdog *(test)*

* Internal service watchdogs.

## Security

### Access Control

* Role-Based Access Control (RBAC).
* Fine-grained permissions.
* Multi-user support.

## Content filter

* Web Filter
* DNS Filter

### System Hardening *(planned)*

* AppArmor configuration and policy management.

### General Auditing

* Internal system/config auditing.

### auditd *(planned)*

* auditd configuration and log management.

### Discovery/Detection

* Host event detection.
* Network topology Discovery.
* Anomalies/services detection in networks *(planned)*

## HA

* contrackd *(dev)*

### IDS / IPS *(planned)*

* IDS/IPS support.

## API & Automation *(draft/dev)*

* REST API with token-based authentication.
* Complete configuration management through the API.
* Every feature available in the web interface is also available through the API.
* *NOTE*: The current API is not the final version, it was developed as an initial interface to enable black box testing of the software. A probably significant API redesign is planned for the future.

## Telemetry System

The telemetry system is a generic, subsystem-agnostic pub/sub pipeline that collects, routes, stores, and exports operational data between components and external services.
While the initial producer is the eBPF subsystem, the pipeline is designed to support other services and modules.
Note: External connectors not available yet

## Other Services

* DHCP Server
* NTP Client/Server (Chrony)
* DNS Server *(planned)*

# Architecture

Styx is a Linux-native management platform built around the networking and security features already provided by the Linux kernel.

It provides a single configuration and management interface for components such as:

* Linux networking and routing
* nftables
* IPsec / XFRM
* Traffic Control (TC)
* eBPF
* Linux services and system components

Styx uses a unified configuration model and applies the configuration to the appropriate Linux subsystems. Runtime state, events, statistics, and logs are collected back into the platform for monitoring and automation.

Each subsystem is managed independently while exposing a consistent interface through the web UI and API.

## Platform

* Configuration backup and restore.
* Unified configuration model with separate running and startup configurations.
* System and networking logs.
* Telemetry bus (pub/sub).
* Session-based and token-based authentication.
* UI and backend can be deployed separately.
* The backend can listen only on localhost and be accessed remotely through an SSH tunnel, without exposing the management API directly to the network.
* Debian based


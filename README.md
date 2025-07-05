# Cisco Packet Tracer - LC Solicitors Network Design

## 📋 Project Overview

This repository contains a comprehensive network design and implementation for **LC Solicitors**, a law firm operating across London and Manchester offices. The project demonstrates enterprise-level network architecture using Cisco Packet Tracer, featuring secure inter-office connectivity, VLAN segmentation, and dual-stack IPv4/IPv6 implementation.

## 🎯 Project Objective

Build a two-office network infrastructure where:
- **London Office** and **Manchester Office** are connected through WAN technology
- Each office has its own **Admin team** and **Lawyer team** with separate network segments
- Secure, reliable communication between both locations
- Scalable design to accommodate future growth

## 🏢 Business Requirements

LC Solicitors required a robust network infrastructure to:
- Connect London and Manchester offices securely
- Support efficient communication between locations
- Accommodate future expansion (60+ employees total)
- Ensure reliable file sharing, video conferencing, and cloud services
- Maintain high security standards for sensitive legal data

## 🌐 Network Architecture

### Office Layout
- **Left Side**: London Office
- **Right Side**: Manchester Office
- **Connection**: WAN technology linking both locations

### IP Addressing Scheme

#### London Office
| VLAN | Purpose | Network | Gateway | Subnet Mask |
|------|---------|---------|---------|-------------|
| Admin VLAN | Administrative staff | 192.168.1.0/24 | 192.168.1.1 | 255.255.255.0 |
| Lawyer VLAN | Legal professionals | 192.168.2.0/24 | 192.168.2.1 | 255.255.255.0 |

#### Manchester Office
| VLAN | Purpose | Network | Gateway | Subnet Mask |
|------|---------|---------|---------|-------------|
| Admin VLAN | Administrative staff | 192.168.3.0/24 | 192.168.3.1 | 255.255.255.0 |
| Lawyer VLAN | Legal professionals | 192.168.4.0/24 | 192.168.4.1 | 255.255.255.0 |

*Each network supports 50+ devices with room for expansion*

## 🔧 Hardware Components

### Router: Cisco 4321 Series
- **Purpose**: Branch office connectivity
- **Throughput**: 50-100 Mbps aggregate
- **Features**: 
  - 1 NIM slot for WAN/LAN connectivity
  - 2 onboard WAN/LAN ports
  - Built-in VPN support (IPsec, SSL, DMVPN)
  - Energy-efficient design
- **Cost**: £60 per unit

### Switch: Cisco 2960 Series
- **Ports**: Up to 48 Ethernet ports
- **Speed**: 10/100/1000 Mbps
- **Management**: CLI and web-based GUI
- **Features**: QoS, PoE support, comprehensive security
- **Cost**: £67 per unit

### Access Points: Cisco Meraki MX65X
- **Security**: UTM features, firewall, advanced malware protection
- **Connectivity**: 12 Ethernet ports, 8 PoE ports
- **VPN**: Site-to-site and client VPN capabilities
- **Throughput**: 100-250 Mbps
- **Ideal for**: Small to medium-sized offices

## 🌍 WAN Technology Options

### Recommended: MPLS (Multi-Protocol Label Switching)
- **Best for**: High security, reliability, and stable performance
- **Benefits**: Guaranteed service levels, traffic engineering capabilities

### Alternative Options:
- **Leased Lines**: High-performance, minimal latency, maximum security
- **Broadband**: Cost-effective for smaller operations with flexible requirements

### Bandwidth Specification
- **Recommended**: 100 Mbps symmetrical
- **Rationale**: Supports 60 employees across both locations
- **Services**: File sharing, video conferencing, cloud applications

## 📊 Network Performance Monitoring

### Hardware Tools

#### Fluke Network OptiView XG
- **Features**: Automated discovery, real-time analysis
- **Capabilities**: LAN and WAN performance checking
- **Benefits**: Proactive monitoring and reactive troubleshooting
- **Portability**: Easy to carry and install in different locations

#### Cisco Nexus Data Broker
- **Performance**: High-density traffic analysis up to 400G
- **Scalability**: Expands monitoring regardless of ports, switches, or taps
- **Cost-effectiveness**: Reduces network monitoring expenses

### Software Tools

#### Wireshark
- **Type**: Free and open-source packet analyzer
- **Features**: Wide protocol support, real-time analysis
- **Customization**: Suitable for various analysis needs
- **Ideal for**: Network troubleshooting and protocol development

#### SolarWinds Network Performance Monitor (NPM)
- **Features**: Comprehensive monitoring with user-friendly interface
- **Scalability**: Fits networks of different sizes
- **Benefits**: Continuous performance monitoring and troubleshooting

### Key Performance Metrics

#### Latency
- **Definition**: Duration of data packet travel from source to destination
- **Importance**: Critical for VoIP and video conferencing
- **Tools**: Ping, traceroute, SolarWinds NPM, PRTG Network Monitor

#### Bandwidth
- **Definition**: Maximum data transmission rate (bps)
- **Importance**: Enables fast data movement and streaming services
- **Tools**: Speedtest, SolarWinds NPM, PRTG Network Monitor, iPerf

#### Packet Loss
- **Definition**: Percentage of packets that never reach destination
- **Impact**: Causes data retransmission and reduced performance
- **Tools**: Ping, Wireshark, SolarWinds NPM, PRTG Network Monitor

#### Jitter
- **Definition**: Variation in packet delay timing
- **Impact**: Causes choppy audio/video in real-time communication
- **Tools**: Ping, traceroute, Wireshark, SolarWinds NPM

## 🔐 IPv6 Implementation

### Dual-Stack Approach
The network implements both IPv4 and IPv6 protocols simultaneously, ensuring:
- **Compatibility**: Smooth transition while maintaining legacy support
- **Scalability**: Expanded address space for future growth
- **Performance**: Reduced NAT requirements, lower latency
- **Security**: Built-in IPsec capabilities

### IPv6 Addressing Scheme
**Base Allocation**: `2001:db8::/32` (ISP-provided)

#### London Office
- **Admin VLAN**: `2001:db8:1:0::/64`
- **Lawyer VLAN**: `2001:db8:1:1::/64`

#### Manchester Office
- **Admin VLAN**: `2001:db8:4:0::/64`
- **Lawyer VLAN**: `2001:db8:4:1::/64`

### Address Structure
- **Global Prefix**: `2001:db8::/32`
- **Site ID**: Differentiates office locations
- **Subnet ID**: Separates VLANs within each office
- **Interface ID**: Unique device identifier

### Benefits of Dual-Stack Implementation
- **Transition Ease**: Controlled upgrade from IPv4 to IPv6
- **User Experience**: Maintains connectivity during transition
- **Future-Proofing**: Ready for technological expansion
- **Enhanced Security**: Built-in IPv6 security features



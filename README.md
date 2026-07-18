# 01-virtual-network
A hands-on virtual network security lab focused on VM communication, network segmentation, firewall rules, and traffic monitoring.

# Virtual Network Security Lab

## Overview

This project documents the creation of an isolated virtual network security laboratory.

The lab will be used to learn networking, virtualization, firewall configuration, network segmentation, traffic analysis, logging, and security monitoring.

It will later become the foundation for additional projects involving Active Directory, SIEM, incident response, security automation, and AI-powered SOC agents.

## Objectives

* Create an isolated virtual network
* Configure communication between virtual machines
* Deploy a virtual router and firewall
* Provide controlled internet access to laboratory systems
* Separate corporate systems from the attacker network
* Monitor and analyze network traffic
* Document configurations, tests, problems, and solutions

## Planned Architecture

The initial laboratory will contain:

* One virtual firewall/router
* One Windows client
* One Linux server
* One isolated internal network
* One controlled connection to the internet

Additional systems will be added in later stages:

* Windows Server with Active Directory
* Additional Windows clients
* Kali Linux
* SIEM and log collection server
* Security monitoring and incident response tools

## Technologies

Planned technologies include:

* VirtualBox, VMware Workstation, or Proxmox
* OPNsense or pfSense
* Windows 11
* Ubuntu Server
* Kali Linux
* Wireshark

## Project Status

Current stage: Repository setup and network planning.

## Repository Structure

```text
.
├── README.md
├── diagrams/
├── documentation/
├── configurations/
├── screenshots/
└── troubleshooting/
```

## Security Notice

This laboratory is intended only for authorized learning and testing.

Attack simulations will be performed exclusively inside isolated virtual networks. Sensitive files, credentials, virtual machine disks, raw logs, and private network captures will not be uploaded to this repository.

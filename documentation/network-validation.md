# Network Validation

## Overview

This document records the validation of the initial virtual network laboratory.

The Ubuntu Server virtual machine is connected only to the internal VirtualBox network named `LAB-LAN`.

Internet access, DHCP, DNS, and routing are provided by the OPNsense firewall.

## Current Architecture

```text
Internet
   |
VirtualBox NAT
   |
OPNsense WAN
10.0.2.15/24
   |
OPNsense LAN
10.10.20.1/24
   |
LAB-LAN
   |
Ubuntu Server
10.10.20.x/24
```
## Commands Used

The following commands were used to validate the Ubuntu Server network configuration:

```bash
ip address
ip route
ping -c 4 10.10.20.1
ping -c 4 8.8.8.8
ping -c 4 ubuntu.com
sudo systemctl status ssh.socket
sudo ss -tlnp | grep ':22'
sudo apt update
sudo apt upgrade -y
```
## Inter-VM Connectivity Test

A Windows 11 client successfully connected to the Ubuntu Server through SSH over the isolated `LAB-LAN` network.

```powershell
ssh cratos405@10.10.20.186

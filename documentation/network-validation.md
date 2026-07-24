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
```
## Windows Firewall Observation

The Windows 11 client could successfully initiate connections to the Ubuntu Server.

The following tests were successful:

- Windows successfully pinged the Ubuntu Server.
- Windows successfully connected to the Ubuntu Server through SSH.
- Ubuntu replied to connections initiated by Windows.

The Ubuntu Server could not initiate ICMP echo requests toward the Windows client because inbound ping requests are blocked by Windows Defender Firewall by default.

The Windows firewall was intentionally left unchanged because inbound ICMP traffic was not required for the current laboratory objectives.

This behavior demonstrates that a failed ping does not always indicate a network connectivity problem. Host-based firewall rules can block specific types of inbound traffic while allowing established connections and other services.

## ATTACK-LAN Segmentation Validation

The Kali Linux attack machine was configured with the following network settings:

- Hostname: ATK-Kali01
- IP address: 10.10.50.10/24
- Default gateway: 10.10.50.1
- Network: ATTACK-LAN

Connectivity tests confirmed:

- Kali can access the internet.
- Kali can resolve DNS names through OPNsense.
- Kali cannot access the LAB-LAN network.
- Traffic from ATTACK-LAN to LAB-LAN is blocked by OPNsense firewall rules.

This confirms that the attacker network is successfully isolated from the internal laboratory network.

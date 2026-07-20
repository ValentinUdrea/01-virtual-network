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

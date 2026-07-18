# Hardware Requirements and Host System

## Host System

The virtual network security lab is hosted on an ASUS VivoBook X570ZD laptop.

### Hardware Specifications

* **Processor:** AMD Ryzen 5 2500U with Radeon Vega Mobile Graphics
* **Physical cores:** 4
* **Logical processors:** 8
* **Installed memory:** 32 GB RAM
* **System architecture:** x64
* **BIOS mode:** UEFI
* **Secure Boot:** Enabled
* **Hardware virtualization:** Enabled
* **Second Level Address Translation:** Supported

### Host Operating System

* **Operating system:** Microsoft Windows 10 Home
* **Version:** 22H2
* **Build:** 19045

## Virtualization Platform

The initial virtualization platform selected for this project is Oracle VirtualBox.

VirtualBox will be used to create isolated virtual networks and run the firewall, Windows, and Linux virtual machines.

## Initial Resource Allocation

| Virtual Machine   | Virtual CPUs | Memory | Virtual Disk |
| ----------------- | -----------: | -----: | -----------: |
| OPNsense Firewall |            2 |   2 GB |        20 GB |
| Ubuntu Server     |            2 |   2 GB |        25 GB |
| Windows Client    |            2 |   4 GB |     50–60 GB |

Virtual disks will use dynamically allocated storage where possible.

## Capacity Considerations

The host has sufficient memory to run the initial three virtual machines simultaneously.

Because the processor has four physical cores, the number of simultaneously active virtual machines will be limited to avoid excessive CPU contention.

Larger services such as Active Directory and SIEM will be added gradually. Not every laboratory system will need to run simultaneously.

## Storage Requirements

The available storage capacity must be verified before the virtual machines are created.

Recommended free storage:

* **Minimum for the initial network lab:** 120 GB
* **Recommended for future expansion:** 250 GB or more

Virtual machine disks, ISO images, snapshots, and raw logs will not be uploaded to GitHub.

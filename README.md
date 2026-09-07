# 🔐 Cybersecurity and Pen testing Lab Setup
## 📌 Project Overview

This project focuses on setting up a basic cybersecurity laboratory using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to create a controlled virtual environment for learning cybersecurity concepts, Linux networking, network configuration, and future security-testing activities.

The laboratory uses a dedicated virtual network so that additional virtual machines can be added later for authorized cybersecurity practice.

---

## 🎯 Objectives

The main objectives of this project are:

Install the required tools for the virtual lab.
Set up Oracle VirtualBox.
Download and configure Kali Linux.
Create and configure a virtual network using VirtualBox.
Configure the Kali Linux network connection.
Assign the required IPv4 address, gateway, and DNS settings.
Verify the network configuration.
Document the setup process and troubleshooting experience.
Prepare the environment for future cybersecurity exercises.
## 🏗️ Lab Environment

The laboratory environment consists of the following components:

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Security OS | Kali Linux 2026.2 |
| Virtual Network | NatNetwork |
| Kali RAM | 2048 MB |
| Kali IPv4 Address | 10.0.0.2/24 |
| Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |
| Network Configuration Tool | NetworkManager / `nmcli` |

The Kali Linux virtual machine was configured inside VirtualBox and connected to the NatNetwork virtual network. The VM configuration screenshot also shows the allocated memory and virtual machine settings.

## 🛠️ Tools Used

The following tools were used during the lab setup:

7-Zip — used for working with compressed files.
Oracle VirtualBox — used as the virtualization platform.
Kali Linux — used as the cybersecurity-focused operating system.
NetworkManager / nmcli — used to configure the Kali Linux network connection.
🪜 Lab Setup Procedure
### Step 1: Download 7-Zip

7-Zip was accessed/downloaded as part of the preparation for working with compressed files required during the lab setup.

![7-Zip Download](01-7zip-download.png)

The screenshot in the project documentation shows the 7-Zip download page with different available versions and platforms.

### Step 2: Download Kali Linux

Kali Linux was obtained from the official Kali Linux download page.

The Kali download page provides different installation options, including Installer Images and Virtual Machines.

For this lab, the virtual-machine approach was used because Kali Linux was going to run inside Oracle VirtualBox.

![Kali Linux Download Options](02-kali-download.png)

The screenshot shows the Kali Linux download page and the available options for obtaining Kali Linux.

### Step 3: Select VirtualBox as the Virtualization Platform

The Kali Linux virtual-machine download page provides several virtualization platforms.

For this project, VirtualBox was selected as the virtualization platform.

![7-Zip Download](03-virtualbox-option.png)

The screenshot shows VirtualBox among the available virtualization platforms for Kali Linux virtual machines.

### Step 4: Open Oracle VirtualBox

After installing/configuring Oracle VirtualBox, the VirtualBox Manager was opened.

The Kali Linux virtual machine was available in the VirtualBox Manager and could be managed from the main interface.

![7-Zip Download](04-open-virtualbox.png)

The screenshot shows the VirtualBox Manager with the Kali Linux virtual machine and its configuration details.

### 🌐 Step 5: Configure the Virtual Network

A virtual network named NatNetwork was configured in Oracle VirtualBox.

This network provides the virtual networking environment required for the Kali Linux VM.

The Kali Linux VM was then connected to this virtual network through its network adapter.

Network Configuration
Network Name: NatNetwork
Network Type: NAT Network
IPv4 Network: 10.0.0.0/24
![7-Zip Download](07-network-configuration.png)

The screenshot shows the VirtualBox network configuration interface and the NatNetwork network.

### 🖥️ Step 6: Configure Kali Linux Virtual Machine

The Kali Linux virtual machine was configured in VirtualBox.

The VM configuration included the required system resources and network adapter settings.

The VM was allocated:

RAM: 2048 MB

The VM was configured to use the VirtualBox NatNetwork.
![7-Zip Download](08-kali-vm-settings.png)

The screenshot shows the Kali Linux VM settings, including the system configuration and network adapter configuration.


### ⚙️ Step 7: Configure Kali Linux Network

During the network configuration process, the graphical Edit Connection option was not available.

Because of this limitation, the network configuration was performed using the NetworkManager command-line utility (nmcli).

The following network parameters were configured:

IP Address: 10.0.0.2/24
Gateway:    10.0.0.1
DNS:        8.8.8.8

The connection was then restarted using NetworkManager commands.

The configuration was successfully activated and the IP address was verified using:

ip addr show eth0

This troubleshooting step is documented in the Word file, including the reason for using nmcli and the resulting IP configuration.

![7-Zip Download](09-kali-network-configuration.png)

The screenshot shows the Kali Linux terminal where the network configuration was performed using NetworkManager commands.

🔎 Network Verification

After configuring the network connection, the assigned IP address was checked using:

ip addr show eth0

The required IP address was:

10.0.0.2/24

The complete network configuration was:

Setting	Value
IPv4 Address	10.0.0.2/24
Gateway	10.0.0.1
DNS	8.8.8.8
Interface	eth0

The IP address was successfully verified after restarting the network connection.

## 🐞 Problem Encountered & Solution
### Problem: Graphical Network Configuration Option Unavailable

While configuring the Kali Linux IP address, the graphical “Edit Connection” option was not available.

As a result, the IPv4 settings could not be configured through the graphical interface.

### Solution

To resolve the issue, the NetworkManager command-line utility (nmcli) was used.

The required network parameters were manually configured:

IP Address: 10.0.0.2/24
Gateway:    10.0.0.1
DNS:        8.8.8.8

The network connection was then restarted using:

nmcli connection down
nmcli connection up

Finally, the configuration was verified using:

ip addr show eth0

The connection was successfully activated and the required IP address was assigned.


## 📚 What I Learned

Through this lab setup, I learned several practical concepts related to virtualization and cybersecurity environments.

### 1. Virtual Machine Setup

I learned how to prepare and run a Kali Linux virtual machine using Oracle VirtualBox.

### 2. Virtual Networking

I learned how to create and configure a virtual network and connect a virtual machine to that network.

### 3. Linux Network Configuration

I learned how IPv4 addressing, gateways, and DNS settings are configured in Kali Linux.

### 4. Using nmcli

When the graphical network configuration option was unavailable, I learned how to use the NetworkManager command-line utility to configure the network manually.

### 5. Network Verification

I learned how to verify the assigned IP address using:

ip addr show eth0
### 6. Troubleshooting

The network configuration problem helped me understand that Linux networking can be configured through both graphical interfaces and command-line utilities.

### 🔐 Security & Ethical Use

This laboratory is intended for educational and authorized cybersecurity practice.

Any scanning, vulnerability assessment, penetration testing, or security experimentation performed using this environment should only target:

Systems owned by me
Virtual machines created for testing
Systems for which explicit authorization has been provided

Unauthorized security testing against third-party systems is not permitted.


## ✅ Conclusion

The Week 1 cybersecurity lab setup was completed by preparing the required virtualization tools, configuring Kali Linux in Oracle VirtualBox, creating the NatNetwork environment, and configuring the Kali Linux network settings.

A graphical network-configuration limitation was encountered during the setup. This was resolved by using nmcli to manually configure the IP address, gateway, and DNS settings.

The final Kali Linux network configuration used:

IP Address: 10.0.0.2/24
Gateway:    10.0.0.1
DNS:        8.8.8.8

This laboratory provides a foundation for future cybersecurity and penetration-testing exercises in a controlled environment.

## 🔗 Resources
- [7-Zip Official Website](https://www.7-zip.org/)
- [VirtualBox Official Website](https://www.virtualbox.org/)
- [Kali Linux Official Website](https://www.kali.org/)
## 👤 Author
HAMDA RAZA


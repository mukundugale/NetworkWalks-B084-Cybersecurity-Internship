# 🔐 Cybersecurity Lab Environment Setup

Building a virtual lab for cybersecurity and ethical hacking practice.

---

## 📌 Project Overview

This project documents the setup of a cybersecurity testing environment using Oracle VirtualBox and Kali Linux as part of my cybersecurity internship at NetworkWalks.

The purpose is to create a controlled environment for learning network scanning, reconnaissance, vulnerability assessment, and authorized security testing.

The lab will use a private virtual network so that additional virtual machines can be added for future practical exercises.

---

## 🎯 Objectives

The main objectives of this project are to:

- Set up Oracle VirtualBox on an Ubuntu host.
- Add Kali Linux as a virtual machine.
- Create a NAT Network using the `10.0.0.0/24` subnet.
- Configure Kali Linux with the required IP address.
- Verify internet connectivity and DNS resolution.
- Enable clipboard sharing and drag-and-drop.
- Configure the host's `/downloads` folder as a shared folder.
- Create a virtual machine snapshot.
- Document the configuration and verification process.

---

## 🛡️ Purpose of the Lab

This laboratory is intended for cybersecurity education and authorized security testing.

It will provide a controlled environment for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Web application security testing
- API security testing
- Security tool experimentation
- Exploitation practice in authorized environments

**Important:** Security testing must only be performed against systems you own or have explicit permission to test.

---

## 🏗️ Lab Architecture

The Ubuntu host runs Oracle VirtualBox, which hosts the Kali Linux virtual machine.

Kali Linux will connect to a VirtualBox NAT Network configured with the required private subnet.

Additional virtual machines may be added to the same NAT Network for future lab exercises.

---

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Host Operating System | Ubuntu Linux |
| Virtualization Platform | Oracle VirtualBox |
| Attacking Machine | Kali Linux |
| Network Type | NAT Network |
| Required Network Address | `10.0.0.0/24` |
| Required Kali IP Address | `10.0.0.2/24` |
| Default Gateway | To be verified |
| DNS Server | To be verified |
| Kali Internet Access | To be tested |

*The configuration values above describe the assignment requirements. Actual settings will be updated after verification.*

---

# 🪜 Lab Setup Procedure

## Step 1. Prepare VirtualBox

Oracle VirtualBox is used to run Kali Linux in a virtual machine on the Ubuntu host.

The downloaded Kali virtual machine configuration was added to VirtualBox.

**Status:** Kali VM added; startup and configuration verification pending.

## Step 2. Create the NAT Network

A dedicated NAT Network must be configured in VirtualBox.

Required configuration:

- Network type: NAT Network
- IPv4 network: `10.0.0.0/24`
- Kali IP address: `10.0.0.2/24`

The NAT Network allows virtual machines connected to the same network to communicate with each other while supporting outbound connectivity.

## Step 3. Configure the Kali VM Network Adapter

The Kali virtual machine's network adapter must be connected to the configured NAT Network.

The network adapter settings will be verified in VirtualBox before testing connectivity.

## Step 4. Configure the Kali Linux Network

The Kali network interface must use the required IPv4 address:

`10.0.0.2/24`

The gateway, DNS configuration, and internet connectivity will also be checked.

## Step 5. Enable VM Integration

The following features must be configured in the virtual machine settings:

- Shared clipboard
- Drag-and-drop
- Shared host folder

The host's `/downloads` folder must be configured as the shared folder specified by the assignment.

## Step 6. Create a VM Snapshot

After completing and verifying the configuration, create a snapshot of the Kali virtual machine.

Suggested snapshot name:

`Clean Kali - Initial Lab Setup`

A snapshot provides a recovery point before future experiments.

---

# 🔎 Lab Verification

The following commands can be used to verify the network configuration.

| Verification | Command | Expected Result |
|---|---|---|
| Check IP address | `ip -br addr` | Kali has the required IP address |
| Check routing | `ip route` | Correct route and gateway |
| Test gateway | `ping -c 4 10.0.0.1` | Successful replies, if the configured gateway is `10.0.0.1` |
| Test internet connectivity | `ping -c 4 1.1.1.1` | Successful replies |
| Test DNS resolution | `ping -c 4 google.com` | Domain resolves and connectivity succeeds |

The gateway address must be confirmed from the actual VirtualBox NAT Network configuration before using it as a definitive test.

### Verification Results

Results will be recorded after the tests have been performed.

- Kali IP address: Pending verification
- Gateway connectivity: Pending verification
- Internet connectivity: Pending verification
- DNS resolution: Pending verification
- Shared folder: Pending verification
- Clipboard and drag-and-drop: Pending verification
- VM snapshot: Pending verification

---

# 🐞 Problems Encountered & Solutions

Any issues encountered during setup will be documented here, together with the troubleshooting steps and verified solution.

No troubleshooting issues have been documented yet.

---

# 💡 What I Learned

This project is intended to develop practical knowledge of:

### 1. Virtualization

Understanding how virtual machines run a separate operating system on a host computer.

### 2. VirtualBox Networking

Learning how NAT Network configuration supports communication between virtual machines and outbound network connectivity.

### 3. IPv4 Addressing

Practising IP addressing, subnet masks, routing, and connectivity verification.

### 4. Lab Preparation

Preparing a controlled environment for future security testing and practical exercises.

### 5. Technical Documentation

Recording configuration details, verification results, and troubleshooting steps in a reproducible format.

---

# 🔐 Security & Ethical Use

This laboratory is intended for educational purposes and authorized cybersecurity testing only.

All testing will be performed in environments where permission has been granted.

---

# 🔗 Tools & Resources

- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [Kali Linux VirtualBox Documentation](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/)

---

# 👤 Author

**Name:** Your Name  
**Program:** NetworkWalks Cybersecurity Internship  
**Batch:** B084B  
**Task:** WK1-PM1 — Cybersecurity Lab Setup

---

# 📌 Project Information

- Week: 01
- Project: VirtualBox and Kali Linux Lab Setup
- Host OS: Ubuntu Linux
- Repository: Cybersecurity Internship Portfolio

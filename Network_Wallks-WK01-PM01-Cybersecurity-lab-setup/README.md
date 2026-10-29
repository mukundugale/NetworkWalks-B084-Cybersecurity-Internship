# 🔐 Cybersecurity Lab Environment Setup

Building a virtual lab for cybersecurity and ethical hacking practice.

## 📌 Project Overview

This project documents the setup and configuration of a cybersecurity lab using Oracle VirtualBox and Kali Linux on an Ubuntu host. It was completed as part of the NetworkWalks Cybersecurity Internship.

The lab provides a controlled environment for learning network reconnaissance, port scanning, vulnerability assessment, and authorized security testing.

The network is configured to support additional virtual machines for future practical exercises.

## 🎯 Objectives

- Set up Oracle VirtualBox on Ubuntu Linux.
- Import and configure Kali Linux as a virtual machine.
- Create a NAT Network using the `10.0.0.0/24` subnet.
- Configure Kali Linux with the required static IP address.
- Verify gateway connectivity, internet access, and DNS resolution.
- Configure a shared folder between Ubuntu and Kali Linux.
- Configure shared clipboard and drag-and-drop integration.
- Create a baseline VM snapshot.
- Document the configuration, verification, and troubleshooting process.

## 🛡️ Purpose of the Lab

This laboratory is intended for cybersecurity education and authorized security testing.

Planned activities include:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Web application security testing
- API security testing
- Security tool experimentation
- Exploitation practice in authorized environments

**Ethical use:** Testing will only be performed against systems owned by me or for which I have explicit permission.

## 🏗️ Lab Architecture

The Ubuntu host runs Oracle VirtualBox, which hosts Kali Linux.

Kali connects to a VirtualBox NAT Network configured with the `10.0.0.0/24` subnet. The network provides outbound connectivity and can support communication between virtual machines attached to the same NAT Network.

Additional virtual machines may be added for future lab exercises.

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Host Operating System | Ubuntu Linux |
| Virtualization Platform | Oracle VirtualBox |
| Attacking Machine | Kali Linux |
| Kali VM Version | Kali Linux 2026.3 VirtualBox image |
| Network Type | NAT Network |
| NAT Network Name | `NatNetwork` |
| Network Subnet | `10.0.0.0/24` |
| Kali IPv4 Address | `10.0.0.2/24` |
| Default Gateway | `10.0.0.1` |
| DNS Servers | `1.1.1.1`, `8.8.8.8` |
| Shared Folder | Ubuntu Downloads directory |
| Kali Shared Folder Mount | `/media/sf_Downloads` |
| Baseline Snapshot | `Kali-Week1-Base` |

## 🪜 Lab Setup Procedure

### Step 1: Prepare VirtualBox

Oracle VirtualBox was used to run Kali Linux as a virtual machine on the Ubuntu host.

The prebuilt Kali Linux VirtualBox image was imported into VirtualBox.

**Status:** Completed.

### Step 2: Create the NAT Network

A VirtualBox NAT Network named `NatNetwork` was configured.

| Setting | Value |
|---|---|
| Network Name | `NatNetwork` |
| IPv4 Network | `10.0.0.0/24` |
| Gateway | `10.0.0.1` |
| DHCP | Enabled for dynamically assigned addresses |

The DHCP address range was adjusted to start at `10.0.0.3`, keeping `10.0.0.2` available for Kali's required static address.

**Status:** Completed.

### Step 3: Configure the Kali Network Adapter

The Kali virtual machine's network adapter was connected to the `NatNetwork` NAT Network.

The adapter was confirmed to be connected.

**Status:** Completed.

### Step 4: Configure the Kali Linux Network

Kali Linux was configured with the required static IPv4 address.

```text
IP Address: 10.0.0.2/24
Gateway:    10.0.0.1
DNS:        1.1.1.1, 8.8.8.8
```

NetworkManager was configured to use the static address instead of DHCP for the Kali network connection.

**Status:** Completed.

### Step 5: Configure the Shared Folder

The Ubuntu host's Downloads directory was configured as a VirtualBox shared folder.

The folder was mounted in Kali at:

```text
/media/sf_Downloads
```

A test file was created from Kali:

```bash
touch /media/sf_Downloads/kali_test.txt
```

The file was subsequently confirmed to be visible in the host's Downloads directory.

This verified that file creation from the guest was reflected on the host.

**Status:** Completed.

### Step 6: Configure VM Integration

The following VirtualBox integration settings were intended for configuration:

- Shared Clipboard: Bidirectional
- Drag-and-Drop: Bidirectional

**Status:** Confirm that both features work before marking this step fully verified.

### Step 7: Create a Baseline Snapshot

A VirtualBox snapshot was created after configuring the network and shared folder.

```text
Snapshot Name: Kali-Week1-Base
```

The snapshot provides a recovery point before future lab experiments.

**Status:** Completed.

## 🔎 Lab Verification

### Network Verification Commands

The following commands were used to inspect the network configuration and test connectivity.

| Verification | Command | Result |
|---|---|---|
| Check IP address | `ip -br addr show eth0` | `10.0.0.2/24` confirmed |
| Check routing | `ip route` | Default route via `10.0.0.1` confirmed |
| Test gateway | `ping -c 3 10.0.0.1` | Successful; 0% packet loss |
| Test internet connectivity | `ping -c 3 1.1.1.1` | Reported successful |
| Test DNS resolution | `ping -c 3 google.com` | Reported successful |
| Check shared folder mount | `ls -la /media/` | `/media/sf_Downloads` present |
| Test shared folder write access | `touch /media/sf_Downloads/kali_test.txt` | File creation successful |
| Verify host visibility | Check Ubuntu Downloads directory | Test file confirmed on host |
| Verify snapshot | VirtualBox Snapshots view | `Kali-Week1-Base` present |

### Routing Configuration

The `ip route` output confirmed the following routes:

```text
default via 10.0.0.1 dev eth0 proto static metric 100
10.0.0.0/24 dev eth0 proto kernel scope link src 10.0.0.2 metric 100
```

This confirms that traffic to destinations outside the local subnet is routed through `10.0.0.1`.

### Shared Folder Verification

The shared folder appeared at `/media/sf_Downloads`.

The test file was created in Kali and confirmed to be visible on Ubuntu, demonstrating successful guest-to-host file sharing.

## 🐞 Problems Encountered & Solutions

### 1. Kali Initially Received the Wrong IP Address

**Problem:** Kali initially received `10.0.0.3` through DHCP instead of the required `10.0.0.2`.

**Investigation:** The VirtualBox DHCP server was configured to use `10.0.0.2` as its own address.

**Solution:** The DHCP server address was changed to `10.0.0.254`, and the DHCP range was configured to start at `10.0.0.3`. Kali was then configured with the static address `10.0.0.2/24`.

### 2. NetworkManager Rejected the Manual Configuration

**Problem:** NetworkManager rejected the change to manual IPv4 configuration because no static address had been configured yet.

**Solution:** The IPv4 address was configured first, followed by the gateway and DNS settings. The connection was then switched to manual IPv4 configuration and reactivated.

### 3. Shared Folder Path Case Sensitivity

**Problem:** Accessing `/media/sf_downloads` failed because the mounted folder used a capital `D`.

**Solution:** The correct path, `/media/sf_Downloads`, was used.

**Lesson learned:** Linux filesystem paths are case-sensitive.

## 💡 What I Learned

### 1. Virtualization

Learned how to import and configure a virtual machine in VirtualBox.

### 2. VirtualBox Networking

Practised configuring a NAT Network and understanding the relationship between the gateway, DHCP server, and guest virtual machines.

### 3. IPv4 Addressing and Routing

Configured a static IPv4 address, subnet mask, default gateway, and DNS servers. Verified the resulting routing table.

### 4. Network Troubleshooting

Used `nmcli`, `ip route`, `ifconfig`, and `ping` to investigate and resolve network configuration issues.

### 5. Shared Folders

Configured a host-to-guest shared folder and verified file creation from Kali.

### 6. Snapshot Management

Created a baseline snapshot to provide a recovery point before subsequent lab exercises.

### 7. Technical Documentation

Recorded the lab configuration, verification results, and troubleshooting solutions for reproducibility.

## 🔐 Security & Ethical Use

This laboratory is intended for educational purposes and authorized cybersecurity testing only.

Testing will only be performed against systems owned by me or for which permission has been granted.

## 🔗 Tools & Resources

- [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [Kali Linux VirtualBox Documentation](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/)

## 👤 Author

**Name:** Mukund Ugale  
**Program:** NetworkWalks Cybersecurity Internship  
**Batch:** B084
**Task:** WK1-PM1 — Cybersecurity Lab Setup

## 📌 Project Information

- **Week:** 01
- **Project:** VirtualBox and Kali Linux Lab Setup
- **Host OS:** Ubuntu Linux
- **Repository:** Cybersecurity Internship Portfolio

# Using-Virtualization-Hyper-V-

# Assisted Lab: Using Virtualization (Hyper-V)

## Overview

In this lab, I explored the fundamentals of **virtualization** using **Microsoft Hyper-V on Windows Server 2019**.

Virtualization is a key technology in modern IT and cybersecurity environments because it allows organizations to create isolated virtual systems, improve resource utilization, and safely test applications and security configurations.

As a security team member at **Structureality Inc.**, this lab focused on creating and managing virtual machines, configuring virtual networking, and understanding security implications of different virtual switch types.

---

# Lab Scenario

Structureality Inc. is evaluating the benefits and challenges of virtualization.

During this lab, I performed the following tasks:

- Installed the Hyper-V virtualization platform on Windows Server 2019
- Created and configured a new virtual machine
- Installed Windows Server 2019 on the virtual machine
- Configured Hyper-V virtual networking switches
- Connected virtual machines using different network switch types
- Compared security implications of virtual networking

---

# Environment

| Component | Details |
|---|---|
| Host Machine | MS10 |
| Operating System | Windows Server 2019 |
| Virtualization Platform | Microsoft Hyper-V |
| Virtual Machine Created | My Lab VM |
| Guest Operating System | Windows Server 2019 Standard (Desktop Experience) |

---

# CompTIA Security+ Objectives Covered

## Objective 3.1
**Compare and contrast security implications of virtual networking.**

Topics covered:

- Virtual switches
- Private networks
- External networks
- Network isolation
- Virtual machine communication

## Objective 3.2
**Create and configure a virtual machine.**

Topics covered:

- Installing Hyper-V
- Creating virtual machines
- Allocating virtual resources
- Installing operating systems
- Configuring virtual hardware

---

# Part 1: Install Hyper-V

## Steps Performed

1. Connected to the **MS10 Windows Server 2019** virtual machine.
2. Opened **Windows PowerShell as Administrator**.
3. Installed Hyper-V using:

```powershell
Install-WindowsFeature -Name Hyper-V -IncludeManagementTools
```

4. Restarted the server to complete the Hyper-V installation.

---

# Part 2: Create a Virtual Machine

## Using Hyper-V Manager

1. Opened:

```
Server Manager → Tools → Hyper-V Manager
```

2. Selected the MS10 host.
3. Created a new virtual machine:

```
Actions → New → Virtual Machine
```

---

## Virtual Machine Configuration

| Setting | Value |
|---|---|
| Name | My Lab VM |
| Generation | Generation 1 |
| Startup Memory | 1024 MB |
| Virtual Hard Disk Size | 90 GB |
| Installation Method | Install OS later |

---

# Virtual Machine Concepts Learned

## Generation 1 vs Generation 2

### Generation 1

- Supports older operating systems
- Uses traditional BIOS firmware
- Supports 32-bit operating systems

### Generation 2

- Uses UEFI firmware
- Supports newer operating systems
- Provides Secure Boot capability
- Does **not** support 32-bit operating systems

---

# Part 3: Install Windows Server 2019 on VM

## Installation Process

Configured the virtual machine DVD drive:

```
Hyper-V Manager
→ My Lab VM
→ Settings
→ DVD Drive
```

Selected the Windows Server 2019 installation media.

---

## Windows Installation Settings

Selected:

- Windows Server 2019 Standard (Desktop Experience)
- Custom installation
- New virtual disk installation

Created administrator password:

```
Pa$$w0rd
```

---

# Part 4: Configure Hyper-V Virtual Networking

Hyper-V provides different virtual switch types that control communication between virtual machines, the host, and external networks.

Opened:

```
Hyper-V Manager
→ Virtual Switch Manager
```

---

# Virtual Switch Types

## 1. Private Switch

Created:

```
Private Lab Switch
```

### Security Characteristics

A Private switch allows communication:

✅ VM → VM

Does not allow:

❌ VM → Host  
❌ VM → External Network

### Security Use Case

Private switches are useful for:

- Malware analysis environments
- Security testing labs
- Isolated penetration testing networks

---

## 2. External Switch

Created:

```
External Lab Switch
```

Configured:

```
Connection Type:
External Network

Adapter:
Microsoft Hyper-V Network Adapter
```

### Security Characteristics

An External switch allows:

✅ VM → VM  
✅ VM → Host  
✅ VM → External Network

### Security Considerations

Because virtual machines can access external networks:

- Increased exposure to threats
- Requires proper firewall rules
- Requires network monitoring
- Should be used carefully in production environments

---

# Virtual Networking Comparison

| Switch Type | VM Communication | Host Access | External Network |
|---|---|---|---|
| Private | Yes | No | No |
| Internal | Yes | Yes | No |
| External | Yes | Yes | Yes |

---

# Security Considerations of Virtualization

## Benefits

✅ Isolation between systems  
✅ Safe testing environments  
✅ Efficient resource usage  
✅ Easy backup and recovery  
✅ Supports cybersecurity labs  

---

## Risks

⚠ VM escape vulnerabilities  
⚠ Misconfigured virtual switches  
⚠ Shared resources between systems  
⚠ Network segmentation issues  
⚠ Unauthorized VM creation  

---

# Key Commands Used

Install Hyper-V:

```powershell
Install-WindowsFeature -Name Hyper-V -IncludeManagementTools
```

---

# Lab Questions and Answers

## What option is below Virtual Machine?

**Answer:**

```
Hard Disk
```

---

## Does Generation 2 support 32-bit operating systems?

**Answer:**

```
No
```

---

## What file extension is used for bootable installation images?

**Answer:**

```
ISO
```

---

## What is the first option for Virtual Switch Type?

**Answer:**

```
External
```

---

# Skills Demonstrated

- Microsoft Hyper-V administration
- Virtual machine deployment
- Windows Server configuration
- Virtual networking
- Network segmentation concepts
- Security isolation techniques
- Infrastructure security fundamentals

---

# Real-World Cybersecurity Applications

Understanding virtualization is important for cybersecurity roles because security professionals frequently use virtual environments for:

- Security testing
- Malware analysis
- SOC analyst training labs
- Incident response simulations
- Vulnerability assessments
- Network monitoring practice

---

# Conclusion

This lab provided hands-on experience with Microsoft Hyper-V and demonstrated how virtualization technologies support modern IT infrastructure.

By configuring virtual machines and virtual switches, I gained practical knowledge of how network isolation, connectivity, and security controls apply within virtualized environments.

These skills directly support CompTIA Security+ objectives and entry-level cybersecurity roles such as **SOC Analyst** and **Security Analyst**.

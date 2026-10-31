# Lab 1: Active Directory Domain Controller Setup

## Overview

In this lab, I configured Windows Server 2022 and promoted it to an Active Directory Domain Controller.

I created a new Active Directory forest and domain named `corp.local`, configured DNS, and verified the Domain Controller's functionality.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | VMware Workstation |
| Server OS | Windows Server 2022 |
| Server Name | DC01 |
| Domain Name | corp.local |
| NetBIOS Name | CORP |
| Server Role | Active Directory Domain Controller |
| DNS Server | DC01 |
| Global Catalog | Enabled |

## Tasks Performed

### 1. Server Configuration
- Renamed the server to DC01.
- Checked network adapter configuration.
- Configured the server's DNS client settings.

### 2. Active Directory Installation
- Installed the Active Directory Domain Services role.
- Promoted the server to a Domain Controller.
- Created a new forest named `corp.local`.
- Configured DNS and Global Catalog.
- Set the Directory Services Restore Mode password.

### 3. DNS Configuration
- Configured DC01 to use itself for DNS resolution.
- Inspected the Active Directory DNS zone.
- Examined DNS SRV records.
- Configured Google DNS (8.8.8.8) as a DNS forwarder.

### 4. Verification and Testing

The following commands were used to verify the configuration:

| Command | Purpose |
|---|---|
| `Get-ADDomain` | Verified domain configuration |
| `Get-ADForest` | Verified forest configuration |
| `Get-Service NTDS, DNS, KDC, Netlogon` | Checked essential services |
| `nslookup corp.local` | Tested internal DNS resolution |
| `netdom query fsmo` | Identified FSMO role holders |
| `dcdiag /q` | Checked Domain Controller health |
| `net share` | Verified SYSVOL and NETLOGON |

### 5. Active Directory Components

Verified the following components:

- Active Directory database (NTDS.dit).
- SYSVOL and NETLOGON shares.
- DNS forward lookup zone.
- Active Directory SRV records.
- Five FSMO roles.


## What I Learned

- How to install and configure Active Directory Domain Services.
- How to create an Active Directory forest and domain.
- Why DNS is essential for Active Directory.
- The purpose of FSMO roles.
- The difference between SYSVOL and NETLOGON.
- How to verify Domain Controller health using PowerShell and DCDIAG.

## Result

Successfully configured Windows Server 2022 as a Domain Controller for the `corp.local` domain and verified its essential Active Directory and DNS services.

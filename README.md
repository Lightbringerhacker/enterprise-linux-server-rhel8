# Enterprise Linux Server - RHEL 8

## Project Overview

Successfully deployed and configured a Red Hat Enterprise Linux 8 server on a Dell PowerEdge R430 system. The project includes storage configuration, network setup, user management, and centralized file-sharing services using NFS and NIS.

---

## Project Objectives

- Install and configure Red Hat Enterprise Linux 8.7
- Configure RAID-based storage
- Create GPT partitions and XFS filesystems
- Configure static IP networking
- Implement NFS (Network File System)
- Implement NIS (Network Information Service)
- Enable secure remote administration using SSH
- Create a multi-user Linux environment

---

## Hardware Configuration

| Component | Details |
|------------|------------|
| Server Model | Dell PowerEdge R430 |
| Processor | Intel Xeon E5-2630 v4 |
| CPU Cores / Threads | 20 Cores / 40 Threads |
| Memory (RAM) | 128 GB |
| Storage Capacity | 2.7 TB |
| RAID Controller | Dell PERC H730 Mini |

---

## Operating System

| Parameter | Details |
|------------|------------|
| Distribution | Red Hat Enterprise Linux |
| Version | RHEL 8.7 |
| Architecture | x86_64 |

---

## Storage Configuration

### Partition Layout

| Partition | Size | Mount Point | Filesystem |
|------------|------------|------------|------------|
| /dev/sda1 | 1 GB | /boot/efi | vfat |
| /dev/sda2 | 1 GB | /boot | xfs |
| /dev/sda3 | 200 GB | / | xfs |
| /dev/sda4 | 50 GB | swap | swap |
| /dev/sda5 | 2.5 TB | /home | xfs |

### Storage Features

- RAID Storage Configuration
- GPT Partition Table
- XFS Filesystem
- Dedicated Home Partition
- Swap Space Configuration

---

## Network Configuration

| Setting | Value |
|------------|------------|
| Network Interface | eno4 |
| IP Address | 10.x.x.x |
| Gateway | 10.x.x.x |
| DNS Server | 10.x.x.x |

### Network Features

- Static IP Address Configuration
- DNS Configuration
- Gateway Configuration
- NetworkManager Management

---

## Services Implemented

### NFS (Network File System)

Configured NFS server to provide centralized file sharing across Linux systems within the network.

### NIS (Network Information Service)

Configured NIS server for centralized user authentication and account management.

### SSH (Secure Shell)

Enabled secure remote administration and server management.

### RPCBind

Configured RPCBind service to support NFS and NIS communication.

---

## System Administration Tasks Performed

- RHEL 8.7 Installation
- RAID Configuration
- GPT Partition Creation
- XFS Filesystem Creation
- Static Network Configuration
- NFS Server Configuration
- NIS Server Configuration
- SSH Configuration
- User and Group Management
- Service Management using systemctl

---

## Screenshots

The project includes screenshots for:

- Server Hardware Information
- Operating System Information
- CPU Information
- Memory Information
- Partition Layout
- Storage Usage
- RAID Configuration
- NFS Service Status
- NIS Service Status

---

## Technologies Used

- Red Hat Enterprise Linux 8.7
- NFS
- NIS
- SSH
- NetworkManager
- RPCBind
- GPT Partitioning
- XFS Filesystem
- Dell PERC RAID Controller

---

## Author

**Mandar Kanade**

Linux System Administration Project

---

## Project Status

✅ Completed and Tested Successfully

# Enterprise Linux Server - RHEL 8

## Project Overview

Successfully installed and configured Red Hat Enterprise Linux 8 server on Dell PowerEdge R430.

## Implemented Services

- NFS Configuration
- NIS Configuration
- Static IP Configuration
- RAID Storage
- GPT Partitioning
- XFS Filesystem
- Multi-user Environment

# Hardware Details
| Component       | Details               |
------------------------------------------
| Server Model    | Dell PowerEdge R430   |
| CPU             | Intel Xeon E5-2630 v4 |
| Cores/Threads   | 20 Cores / 40 Threads |
| RAM             | 128 GB                |
| Storage         | 2.7 TB                |
| RAID Controller | Dell PERC H730 Mini   |

# Operating System
- Red Hat Enterprise Linux 8.7

# Partition Layout
| Partition | Size   | Mount Point | Filesystem |
-------------------------------------------------
| /dev/sda1 | 1 GB   | /boot/efi   | vfat       |
| /dev/sda2 | 1 GB   | /boot       | xfs        |
| /dev/sda3 | 200 GB | /           | xfs        |
| /dev/sda4 | 50 GB  | swap        | swap       |
| /dev/sda5 | 2.5 TB | /home       | xfs        |

# Network Configuration
| Setting    | Value    |
-------------------------
| Interface  | eno4     |
| IP Address | 10.x.x x |
| Gateway    | 10.x.x.x |
| DNS        | 10.x.x x |


# Services Configured
- NFS
- NIS
- SSH
- NetworkManager
- RPCBind
- 

# Author
Mandar Kanade
Linux System Administration Project

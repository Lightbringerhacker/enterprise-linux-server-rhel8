# NIS Server Configuration on RHEL 8

## Overview
Network Information Service (NIS) provides centralized user authentication and account management across multiple Linux systems. This configuration was performed on a Red Hat Enterprise Linux 8 server to act as the NIS master server.

---
## Prerequisites

- RHEL 8 Installation Media Mounted
- Root Privileges
- Static IP Address Configured
- Hostname Configured

---
## 1. Install Required Packages

Install all packages required for NIS functionality.
```bash
yum install -y yp*
yum install -y nis*
yum install -y ypserv*
yum install -y rpcbind*
yum install -y authconfig*
yum install -y oddjobd*
```
### Package Description
| Package | Purpose |
|----------|----------|
| ypserv | NIS Server Daemon |
| ypbind | NIS Client Binding Service |
| rpcbind | RPC Port Mapping Service |
| nis | NIS Utilities |
| oddjobd | Automatic Home Directory Creation |
| authconfig | Authentication Configuration Tools |


---
## 2. Configure NIS Domain
Set the NIS domain name.
```bash
nisdomainname abc
```
Make the configuration persistent.
```bash
vi /etc/sysconfig/network
```
Add:
```text
NISDOMAIN=abc
```

---
## 3. Configure Hostname Resolution
Configure hostname mapping.
```bash
vi /etc/hosts
```
Add:
```text
12.x.x.x       localhost localhost.localdomain localhost4 localhost4.localdomain4 xyz
::1             localhost localhost.localdomain localhost6 localhost6.localdomain6 xyz
10.x.x.x      cadencedemo
```

Verify hostname.
```bash
hostname
```
Expected Output:
```text
xyz
```

---
## 4. Configure NIS Server Information

Edit the NIS configuration file.

```bash
vi /etc/yp.conf
```
Add:

```text
domain abc server xyz
ypserver xyz
```

---
## 5. Configure System Authentication
Enable NIS authentication.
```bash
authselect select nis --force
```

Enable automatic home directory creation.
```bash
authselect enable-feature with-mkhomedir
```

---
## 6. Disable Firewall and SELinux (Lab Environment)
### Disable Firewall
```bash
systemctl stop firewalld
systemctl disable firewalld
```

### Disable SELinux
```bash
vi /etc/selinux/config
```
Modify:

```text
SELINUX=disabled
```

Reboot the server if required.

---
## 7. Enable Required Services

Start and enable all required NIS services.
```bash
systemctl enable --now rpcbind
systemctl enable --now ypserv
systemctl enable --now ypbind
systemctl enable --now nis-domainname
systemctl enable --now oddjobd
```

Verify service status.
```bash
systemctl status rpcbind
systemctl status ypserv
systemctl status ypbind
```

---
## 8. Verification

Check NIS server binding.

```bash
ypwhich
```

Expected Output:
```text
xyz
```

Display NIS user database.
```bash
ypcat passwd
```

-----
## Services Used
| Service | Purpose |
|----------|----------|
| rpcbind | RPC Communication Layer |
| ypserv | NIS Server Service |
| ypbind | NIS Client Binding Service |
| oddjobd | Home Directory Auto Creation |
| nis-domainname | Maintains NIS Domain Information |


---
## Result
The RHEL 8 server is successfully configured as an NIS server and can provide centralized authentication services to NIS client systems within the configured NIS domain.

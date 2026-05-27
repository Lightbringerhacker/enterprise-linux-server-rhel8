# NFS Configuration
Below command is used to configure server side NFS.

## Install NFS Packages
```bash
   yum install nfs-utils -y
```

## Create Shared Directory
```bash
mkdir /abcd
```

## Configure Exports
```bash
vi /etc/exports
```

Add:
```bash
/abcd 17.3.0.0/255.255.248.0(rw,sync)
```

## Start NFS Service
```bash
systemctl enable --now nfs-server
```

## Export Shares
```bash
exportfs -avr
```

## Verify
```bash
showmount -e
```

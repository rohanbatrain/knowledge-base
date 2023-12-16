## Proxmox Virtual Environment (PVE)

```yaml
Target Harddisk: /dev/sdb WDC WDS240G2G0B
```

### HardDisk Options 

```yaml
Filesystem: xfs
hdsize : 223.0
swapsize: 3
maxroot:  30
minfree: NULL
maxvz: NULL
```

### Location and Time Zone selection

```yaml
Country: India
Time zone: Asia/Kolkata
Keyboard Layout: U.S. English
```

### Administration Password and Email Address

```yaml
Password: ********
Confirm: ********
Email: vina-pve@xxxx.xx
```

### Management Network Configuration

```yaml
Management Interface: enp34s0 
Hostname (FQDN): vina-pve.xxxx.in
IP Address (CIDR): 10.xx.xx.xx/24
Gateway: 10.xx.xx.c
DNS Server: 1.1.1.1
```

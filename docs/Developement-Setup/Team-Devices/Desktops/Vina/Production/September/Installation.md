# Proxmox Virtual Environment (PVE)

Target Harddisk: /dev/sdb WDC WDS240G2G0B

# HardDisk Options 

Filesystem: xfs
hdsize : 223.0
swapsize: 3
maxroot:  30
minfree: NULL
maxvz: NULL

# Location and Time Zone selection

Country: India
Time zone: Asia/Kolkata
Keyboard Layout: U.S. English

# Administration Password and Email Address

Password: ********
Confirm: ********
Email: vina-pve@xxxx.xx

# Management Network Configuration

Management Interface: enp34s0 
Hostname (FQDN): vina-pve.xxxx.in
IP Address (CIDR): 10.0.0.xx/24
Gateway: 10.0.0.1
DNS Server: 1.1.1.1
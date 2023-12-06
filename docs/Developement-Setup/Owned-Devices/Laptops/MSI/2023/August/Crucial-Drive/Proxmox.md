## Proxmox Installation

Fresh Installation and setup.

### Networking 

#### Production 

We assigned 2 ip address to 2 ethernet adapters. 

##### 10.X.X.X.1 - Airtel Xtreme Router

- Laptop Ethernet NIC -  10.X.X.X.2  (vmbr0)
- USB Ethernet adapter - 10.X.X.X.3  (vmbr1)

 
 
##### 11.X.X.X.1 (PFSENSE)

This is the ip schema for pfsense. DHCP on lan is enabled so all vms which have vmbr1 will be given internet access through NAT and also ip which follows the rule 11.x.x.x 

### Proxmox Desktop Environment

We already have installed dwm on proxmox now letsss configure it. 

#### Firefox Setup

I've logged in using my firefox account. I have successfully synced my firefox data to all other operating system running firefox.

##### Extentions 

1. bitwarden
2. Ublock origin

#### Brave Setup

##### Extentions

1. Scribe-how


## Proxmox-Containers

### Pihole 

We used proxmox lxc ubuntu 23.04 template and on top of it installed pihole. 


The steps of creating CT was:

```yaml
hostname: pihole
disk size: 4
Cores: 1
Memory: 1024
swap: 1024
ipv4: static
ipv6: dhcp request
dns domain: pihole.vina.xxxx.xx.x
dns-server: 1.1.1.1
```


#### Installing

1. update the system and install curl
2. go to pihole documentation or directly enter a controversial bash snippet w/o verifying :lol:

```bash
curl -sSL <https://install.pi-hole.net> | bash
```

3. give a static ip to pihole container.
4. autostart=true

## Proxmox Virtual Machines

### pfsense




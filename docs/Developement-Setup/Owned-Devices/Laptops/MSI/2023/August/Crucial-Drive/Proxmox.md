## Proxmox Installation

Fresh Installation and setup.

### Proxmox Network  

We assigned 2 ip address to 2 ethernet adapters. 

#### 10.X.X.X.1 - Airtel Xtreme Router

- Laptop Ethernet NIC -  10.X.X.X.2  (vmbr0)
- USB Ethernet adapter - 10.X.X.X.3  (vmbr1)

 
#### 11.X.X.X.1 (PFSENSE)

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

This is the list of containers that we are running.

- [pihole](./Promox/Containers/Pihole.md)


## Proxmox Virtual Machines

Before proceeding any further, we need to follow thi [link](https://www.reddit.com/r/homelab/comments/b5xpua/the_ultimate_beginners_guide_to_gpu_passthrough/) in order to passthrough pcie devices

### Issues

1. update-grub for iommu ~~command not found [link](https://askubuntu.com/questions/418666/update-grub-command-not-found) turns out grub is installed on manjaro. trying to do same setting on manjaro and seeing if it works.~~
see [IOMMU](./Failure-Log.md)




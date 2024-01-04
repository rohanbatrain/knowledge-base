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

Before proceeding any further, we need to follow thi [link](https://www.reddit.com/r/homelab/comments/b5xpua/the_ultimate_beginners_guide_to_gpu_passthrough/) in order to passthrough pcie devices

### Issues

1. update-grub for iommu ~~command not found [link](https://askubuntu.com/questions/418666/update-grub-command-not-found) turns out grub is installed on manjaro. trying to do same setting on manjaro and seeing if it works.~~
see [IOMMU](/Developement-Setup/Owned-Devices/Laptops/MSI/2023/August/Crucial-Drive/Failure-Log)




### pfsense

We have followed the following blog "pfsense with proxmox" from official site.

#### VM Creation

Pretty straight forward setup same which is followed for a freebsd based system. 

Graphic Card : Spice 
SCSI Controller : Virtio SCSI single 
Bus/Device : Virtio Block
Disk size : 10g
socket : 1 
core : 1
type : host
memory : 2048
network-model : Virtio paravirtualized
Firewall : unticked


#### Post creation
Add a second vmbr1 to your pfsense vm. virtio paravirtualized

#### Installation on vm

Typical normal installation.

#### Configuration

Auto fetch ip on wan from dhcp, go into your router and set a static ip.
Lan = 11.x.x.1 

In order to setup my interfaces i have gone into vmbr and ticked the disconnect option in order to virtually disconnect the bridge. Then gone into pfsense to autodetect the interface again (reconnect when prompted to do so) in order to give it a static lan and wan ip. 

DHCP is enabled on lan in order to give out ip using vmbr1, so if you have a vm with 2 bridges they are going to receive to links

10.x.x.c and a backup 11.x.x.c 

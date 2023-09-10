## Proxmox Installation

Fresh Installation and setup.

### Networking
We have used our github script to install proxmox and post install. then there arose a hurdle that i need to have atleast two network interfaces to install pfsense, but the recommended one was 3, that you have 2 for pfsense and one is left for proxmox management. So creating the first and second virtual bridge was easy but problems were faced when i used a usb based wifi device for my 3rd interface, that theoretically should pop up automatically on proxmox network TAB on host, but it didn't, it was detected with `lsusb` and further i also requested an ip by connecting that wifi using iwctl, but still no sign of it on proxmox dashboard. Thus i directly gone intor /etc/network/interfaces and copied the above syntax and manually added the entry and restarted my proxmox and it worked.

But we dropped installing pfsense on laptop hardware as it in not ideal to run a router lan port on an Access point. Shifted to pihole for internal dns. 

### Cluster

When we dropped the idea of installing pfsense we decided to try out pve-cluster, we tried creating a cluster with our two pve nodes but turns out that the cluster required no vm to be created on each of the instance which would join the cluster so i reinstalled cluster on both instances. Moving on when i joined the proxmox cluster things started to go downhill, we weren't known to the fact that we need both of the nodes running at the same time although that's what a cluster is for (intended to be used on a datacenter) but i thought we would loadbalance pihole etc. but that wasn't the case as we have to boot simuntaneously otherwise our login server of the proxmox ve wouldn't work aswell. we cannot create, start or literally do anything proxmox if the other node is offline. 

As per my experience this should occur when there are only 2 nodes in a cluster. So we are reverting back and removing cluster with the scripts provided on the application

### Firefox Setup

I've logged in using my firefox account. I have successfully synced my firefox data to all other operating system running firefox.

#### Extentions 

1. bitwarden
2. Ublock origin

### Brave Setup

#### Extentions

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




## Till December

### 11.X.X.X.1 (PFSENSE)



### Obsolete (as of Nov-2023)

We have used our github script to install proxmox and post install. then there arose a hurdle that i need to have atleast two network interfaces to install pfsense, but the recommended one was 3, that you have 2 for pfsense and one is left for proxmox management. So creating the first and second virtual bridge was easy but problems were faced when i used a usb based wifi device for my 3rd interface, that theoretically should pop up automatically on proxmox network TAB on host, but it didn't, it was detected with `lsusb` and further i also requested an ip by connecting that wifi using iwctl, but still no sign of it on proxmox dashboard. Thus i directly gone intor /etc/network/interfaces and copied the above syntax and manually added the entry and restarted my proxmox and it worked.

But we dropped installing pfsense on laptop hardware as it in not ideal to run a router lan port on an Access point. Shifted to pihole for internal dns. 



### Cluster (not in production anymore)

When we dropped the idea of installing pfsense we decided to try out pve-cluster, we tried creating a cluster with our two pve nodes but turns out that the cluster required no vm to be created on each of the instance which would join the cluster so i reinstalled cluster on both instances. Moving on when i joined the proxmox cluster things started to go downhill, we weren't known to the fact that we need both of the nodes running at the same time although that's what a cluster is for (intended to be used on a datacenter) but i thought we would loadbalance pihole etc. but that wasn't the case as we have to boot simuntaneously otherwise our login server of the proxmox ve wouldn't work aswell. we cannot create, start or literally do anything proxmox if the other node is offline. 

As per my experience this should occur when there are only 2 nodes in a cluster. So we are reverting back and removing cluster with the scripts provided on the application


## December 2023 

### IOMMU 

I couldn't pass through PCIe devices initially. I attempted to find documentation, which directed me to modify some GRUB flags. After making the changes, however, the issue persisted. Since I was booting with Manjaro's GRUB, I believed adjusting settings there might resolve the problem. Later, I realized this wasn't the case, as such modifications would blacklist Nvidia, resulting in no display.

Upon further investigation, I discovered that my system had an Intel UHD graphics card and an Nvidia RTX 3050 as the 3D controller. Reassured by this, I checked the BIOS for VT-d emulation, confirming it was set to true (1). I then changed the BIOS priority to Crucial, where GRUB for Proxmox was located. Despite these efforts, the problem persisted. Exhausting online guides from the first and second pages of Google, I reached a point of frustration.

As a last resort, I entered root to explore potential missing commands on the shell. Strangely, I noticed that some commands were absent in the shell but present in the noVNC console under the same root. Intuitively, I decided to run a single command: apt dist-upgrade. This action, surprisingly, provided the missing commands, including update-grub. A pop-up indicated that GRUB2 would replace legacy GRUB, explaining why my IOMMU wasn't functioning initially.

After the upgrade, everything worked flawlessly.

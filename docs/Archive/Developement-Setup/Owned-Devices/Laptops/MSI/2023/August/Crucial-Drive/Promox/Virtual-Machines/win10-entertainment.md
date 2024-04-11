## Windows 10 Entertainment 

This windows installation is focused on testing of sketchy softwares or to do low spec gaming  (no gpu passthrough, my particular laptop has support for iommu but the issue is my nvidia is used for 3d, and my display is driven by intel uhd. So when i passthrough both windows give me a sweet screen of bsod and there is absolutely no display on my laptop or external monitor. so in short i have no opengl support. I am going to try use nvidia to game but no idea if that's going to work as an encoder stand alone.) etc. 

### VM Creation

```yaml
agent: 1
balloon: 0
bios: ovmf
boot: order=scsi0;ide0;ide2;net0
cores: 4
cpu: host,flags=+aes
efidisk0: local-lvm:vm-102-disk-0,efitype=4m,pre-enrolled-keys=1,size=4M
ide0: local:iso/Win10_22H2_English_x64v1.iso,media=cdrom,size=5997046K
ide2: local:iso/virtio-win.iso,media=cdrom,size=612812K
machine: pc-q35-8.1
memory: 8192
meta: creation-qemu=8.1.2,ctime=1704469801
name: win10-entertainment
numa: 1
ostype: win10
scsi0: local-lvm:vm-102-disk-1,cache=writeback,discard=on,size=100G
scsihw: virtio-scsi-pci
sockets: 1
vga: std
hostpci0: 0000:00:1f
```

### Configuration

The first thing that i ran is CTT Windows Utility

#### CTT Utility

```ps
iwr -useb https://christitus.com/win | iex
```


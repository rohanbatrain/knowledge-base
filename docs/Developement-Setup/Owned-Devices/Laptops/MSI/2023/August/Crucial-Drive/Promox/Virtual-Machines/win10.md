## Windows 10 

This windows installation is focused on developement and other work related tasks. 

name: win10.sitar-pve

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
name: win10
numa: 1
ostype: win10
scsi0: local-lvm:vm-102-disk-1,cache=writeback,discard=on,size=100G
scsihw: virtio-scsi-pci
sockets: 1
vga: std
hostpci0: 0000:00:1f
```

Passing a tplink wifi adaptor to vm.

Installation

- username : win10

### Configuration

The first thing that i ran is CTT Windows Utility.

```ps
iwr -useb https://christitus.com/win | iex
```

You can use the following to create a config files for CTT

#### Config 1 : Tweaks

```json
[
    "WPFMiscTweaksDisableNotifications",
    "WPFEssTweaksTele",
    "WPFEssTweaksHiber",
    "WPFMiscTweaksDisableUAC",
    "WPFEssTweaksServices",
    "WPFEssTweaksDVR",
    "WPFEssTweaksLoc",
    "WPFEssTweaksRemoveOnedrive",
    "WPFEssTweaksWifi",
    "WPFMiscTweaksDisplay",
    "WPFEssTweaksHome",
    "WPFEssTweaksStorage",
    "WPFEssTweaksAH",
    "WPFEssTweaksOO",
    "WPFEssTweaksTeredo"
]

```

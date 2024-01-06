## Garuda

### VM Config

```yaml
agent: 1
balloon: 0
bios: ovmf
boot: order=scsi0;ide2;net0
cores: 4
cpu: host,flags=+aes
efidisk0: local-lvm:vm-104-disk-0,efitype=4m,pre-enrolled-keys=1,size=4M
ide2: local:iso/garuda-dr460nized-linux-zen-231029.iso,media=cdrom,size=2565330K
machine: q35
memory: 16384
meta: creation-qemu=8.1.2,ctime=1704488190
name: garuda
numa: 1
ostype: l26
scsi0: local-lvm:vm-104-disk-1,discard=on,size=100G
scsihw: virtio-scsi-pci
sockets: 1

```

Disable secure boot in uefi.


### Post-Install

garuda-update using its assistant.


#### Packages 

1. obsidian
2. obs-studio
3. vscodium


## Introduction 

I Bought this laptop after my latitude died and i was looking for a device to use for my college needs. It came with windows 11 pre installed so i am keeping this on the nvme drive which shipped with the laptop and i transferred my crucial 1 tb ssd and installed 32x2 gb ram to max out this laptop. Now on the crucial ssd i am installing proxmox ve. 

## GRUB 

We installed manjaro on top of windows 11 and then we installed proxmox on crucial which lead to 2 grub bootloaders installed, one on efi partition of micron ssd and other on crucial. so we had a choice to run os-prober on either of it. I first tried to add grub entries on proxmox grub but it didn't work so i skipped and made manjaro grub my default one. So now we are running manjaro grub as our main bootloader.

## MICRON NVME drive

We are using this device to store bare metal operating systems. Which would act as our primary operating system when outside of our network, i.e. ethernet connection not working etc. Also, that would act as a failover if proxmox got ripped apart while i test my curiousity. 

1. [Windows-11](./Micron-Drive/Windows-11.md)
2. [Manjaro](./Micron-Drive/Manjaro.md)

## Crucial

This would install proxmox ve, a type-1 hypervisor which would emulate our home lab needs on a budget. Who can buy a true 1U server while being a student. So MSI laptop with 64GB ram would be well enough. I GUESS!!!

1. [Proxmox](./Crucial-Drive/Proxmox.md )
## Packages

1. Obs
2. droidcam

## Thoughts on migration

Migrating from manjaro to garuda was an experiment to see whether this kernel support droidcam v412 loopback, and lucky enough for me it worked. So i am sticking with garuda for my production environment.

## Installation

To be honest, installing garuda was a pain. Initially i installed it on my nvme by simply using calamaras and replacing the manjaro partition and hoping that it will just work, but trying to install garuda thrice using this method all stuck on installing bootloader at 90 percent. So, with my fourth try i installed it and rebooted when it stuck on 90 percent. 

### What's next 

Well initially i am still stuck with no grub and no way to boot into any other os like windows or proxmox (not really as i have an alternate grub installation on crucial sdd.) but keeping that in mind i need a way to boot garuda and for that i need grub to be installed in my micron ssd. 

How?

According to garuda forum, i had to chroot and update the grub using `update-grub` but as usual my life is not simple as that. I had to disable os-prober because it was trying to add an entry of my lxc container from proxmox, which is resulting grub to be stuck on that line forever, adding ubuntu-lts 20.04. So for its prevention i had to disable it. Then i proceeded to updated the system using garuda-update. it has a hell lot of pgp errors so i had to enter 4 lines in order to fix that. You can find those [here](https://raw.githubusercontent.com/rohanbatrain/scripts/main/OS-Specific/Garuda/Post-Installation/00-Post-Install.sh)


## Post Installation 

### Copying required directories

I've taken some backups to external storage, restoring those is the first step. 

1. Projects


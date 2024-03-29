## Packages

We have chaotic-aur preinstalled, so we don't have to rely on paru etc, as pacman already have the ability to build packages (as per my intuitive understanding) still if i use paru for anything, then that would have a sub heading listed here. 

1. Obs
2. droidcam
3. obsidian
4. vlc
5. vscodium

## Thoughts on migration

Migrating from manjaro to garuda was an experiment to see whether this kernel support droidcam v412 loopback, and lucky enough for me it worked. So i am sticking with garuda for my production environment.

## Installation

To be honest, installing garuda was a pain. Initially i installed it on my nvme by simply using calamaras and replacing the manjaro partition and hoping that it will just work, but trying to install garuda thrice using this method all stuck on installing bootloader at 90 percent. So, with my fourth try i installed it and rebooted when it stuck on 90 percent. 

### What's next 

Well initially i am still stuck with no grub and no way to boot into any other os like windows or proxmox (not really as i have an alternate grub installation on crucial sdd.) but keeping that in mind i need a way to boot garuda and for that i need grub to be installed in my micron ssd. 

How?

According to garuda forum, i had to chroot and update the grub using `update-grub` but as usual my life is not simple as that. I had to disable os-prober because it was trying to add an entry of my lxc container from proxmox, which is resulting grub to be stuck on that line forever, adding ubuntu-lts 20.04. So for its prevention i had to disable it. Then i proceeded to updated the system using garuda-update. it has a hell lot of pgp errors so i had to enter 4 lines in order to fix that. You can find those [here](https://raw.githubusercontent.com/rohanbatrain/scripts/main/OS-Specific/Garuda/Post-Installation/00-Post-Install.sh)


## Post Installation 

### Copying required directories (Temporary Solution)

I've taken some backups to external storage, restoring those is the first step. 

1. Projects

### FSTAB Setup

Now the project folder lies in proxmox, so i am symlinking that to my own garuda documents, for that i need to first make a mount point on my garuda /mnt directory. Then mounting that automatically using fstab on each bootup. 

1. greping blkid of pve root using 

```bash
sudo blkid | grep "/dev/mapper/pve-root" | awk -F '"' '{print $2}'
``` 

2. making a directory in mnt

```bash
sudo mkdir /mnt/pve-root
```

3. updating fstab [todo]

### Configuration

1. Configuring Git using this [script](https://raw.githubusercontent.com/rohanbatrain/scripts/main/Application-Specific/Git/initial-setup.sh)

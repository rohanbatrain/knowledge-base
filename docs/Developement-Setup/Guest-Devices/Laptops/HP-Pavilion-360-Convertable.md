# Introduction

I received this laptop with windows 10 as its operating system. I haven't been used to windows for my day to day use and as this is a guest laptop i wasn't allowed to swap hard drives. So i used a usb to sata connector and took my ssd out from my dell latitude and then plugged it in. Here's the walkthrough.


## Installing GNU/Linux's Cachy-OS (June-2023)

These are the steps i followed to use linux without disturbing the guest operating system.

1. Plugged in ssd through usb.
2. Switched to legacy boot support (which automatically switches off secure boot in this particular device's BIOS.)
3. Installed cachyos on SSD


### Directories

Here's what my whole system directory structure looks like:

```
Home/
    Rohan/
        Github/
        Builds/
        Applications/
```

### Updates

I updated the system using pacman traditional route as the installation option i choose was offline, which means it installs the packages from iso rather then fetching from the web. 

### Packages

After updates these are the packages that i installed.

#### Pacman

The following are the packages that have been installed using pacman.

1. firefox
2. python-pip
3. yay
4. veracrypt
5. obs-studio

#### Yay 

1. vscodium-bin : I installed support for marketplace and other features.
2. gitkraken: 

### Application Configs

#### Firefox

1. Logged in using firefox account, for bidirectional sync on all my firefox browsers.

#### Codium

Here's my codium setup:

##### Extentions

1. Python (Microsoft)

### Developement Setup

#### Setting up Git

in order to login to github using my ssh keys i copied my ssh keys to ~/.ssh/ directory but i was getting a too open private key error. So, in order to fix that i made my ssh directory to be 700 and id_rsa to be 600. and now Github is authenticated.


```bash
#!/bin/bash

cd ~/.ssh/
git config --global user.name "Rohan Batra"
git config --global user.email "116573125+rohanbatrain@users.noreply.github.com"
git config --global gpg.format ssh
git config --global commit.gpgsign true
git config --global user.signingkey ~/.ssh/id_rsa.pub
ssh -T git@github.com
```
## Unbrick

This is my production android (kebab) setup, Before reaching to production i hard bricked the device. So unbricking the device using MSM Tool.

## MSM Download tool

You can easily find MSM by doing a simple search query on the internet.


## Going into EDL mode

1. Hard brick state: since i was in a hard brick state, i wasn't even able to go into edl mode by conventional volume rocker method, so tried and found a really helpful tool in xda which was fastboot-edl, it enables us to boot into edl mode if you have access to fastboot. Which i assume you would. 

2. Flashed Oxygen OS 11 Successfully.


## Preparation for migration

A funny incident, i tried to switch slots in recovery and got to know that msm only flashes to slot A, so i actually got myself in kind of a brick state and got into void except fastboot mode, no recovery nothing, Just fastboot and me. But I got a neat trick up my sleeves, as i had fastboot i relocked the bootloader which forced oneplus to switch slots as i wasn't aware of switching slots using fastboot (if that's even possible.) and then proceeded to format the data instead of reusing msm.



### Bootloader unlock

I read somewhere that there are issues in some devices unlocking the bootloader at android 12.1. so, it is recommended to unlock the bootloader first and then perform the local upgrade.

1. Booting into fastboot 
2. Command -> `fastboot oem unlock`
3. Phone will wipe itself out


### Updating to Oxygen OS 13

1. Download links for each of the OOS builds. Downloads for [Android-11](https://oxygenos.oneplus.net/OnePlus8TOxygen_15.I.29_OTA_0290_all_2202182359_abd12ff9474549d3.zip) (2.9 GB) , [Android-12](https://oxygenos.oneplus.net/86_sign_KB2001_11_C_OTA_1350_all_a5deec_00011011.zip) (3.9 GB) OR  [Android-13](https://gauss-componentotacostmanual-sg.allawnofs.com/remove-e8db6ccbcf328d52b602fa5897ddb266/component-ota/22/11/15/471125f26d1447f19aa900c5ba2ee42d.zip) (4.4 GB).

2. Perform local update with these packages.

## Flashing Nameless-AOSP

Why this in production? 

The reasons are simple and straight forward, drop in safety net support, Original camera module and cool custom rom features. No magisk in production as of now.

### Preparation

From [nameless-wiki](https://nameless.wiki/getting-started/install/for_8_9R)

1. Reboot your phone to fastboot mode
2. Open cmd and go to the folder where platform tools are (DO NOT USE POWERSHELL!)

### Flashing

The following files can easily be obtained from nameless-aosp sourceforge.

* Flash boot image

```bash
fastboot flash boot boot.img
```

* Flash vbmeta image

```bash
fastboot flash vbmeta vbmeta.img
```
 
* Flash vbmeta_system image

```bash
fastboot flash vbmeta_system vbmeta_system.img
```

* Flash orangefox recovery

```bash
fastboot boot Orangefox-recovery.img
```

* Flashing nameless-aosp zip from orangefox recovery, wipe cache and you are done.


## Nameless-AOSP Users Config

I have created 4 different users for my android device, this section host the config for each of them respectively.


### Productivity

This account is specifically for professional growth. Be it Business tools, contact or marketing suite. If it has a purpose in making life productive then it goes here.


#### Applications 

This is the list of applications that I use on this user account.


##### Google Play Store

Applications downloaded from the google play store.

1. Tutanota
2. Bitwarden 
3. Telegram
4. Keep Notes
5. Photos by google (unlimited storage)
6. Adobe Scan
7. Obsidian
8. Github 
9. Remini
10. Audio relay
11. KDE-Connect
12. Whatsapp Business
13. Whatsapp Messenger
14. Hubspot CRM
15. Material files

##### Directly from Source

Applications downloaded directly from the source using a browser.

1. F-Droid 
2. DSU sideloader (Github repo) 


##### Using F-Droid

Applications downloaded from the F-droid free and opensource app store. 

1. Aegis Authenticator
2. Termux
3. Amaze File manager
4. Amaze utilities


### Education

This account is specific to all my educational needs, college specific and all other knowledge related tasks resides here.

#### Applications

This is the list of applications that I use on this user account.

##### Google Play Store

Applications downloaded from the google play store.

1. Udemy
2. Khan Academy


### Entertainment

THis account is for all my entertainment needs

#### Applications

This is the list of applications that I use on this user account.

##### Directly from Source

Applications downloaded directly from the source using a browser.

1. TapTap 

##### Google Play Store

Applications downloaded from the google play store.

1. Telegram (All Accounts)
2. Photos ( for gameplay upload )
3. 1.1.1.1 By Cloudflare
4. instagram (Rohanbatrarb)
5. Bitwarden
6. Kde-Connect

##### From TapTap Game Store

1. BGMI 
2. PUBG MOBILE

### Government And Finance

THis account is for all my government needs and personal finance.

#### Applications

This is the list of applications that I use on this user account.

##### Google Play Store

Applications downloaded from the google play store.

1. BHIM
2. Bitwarden
3. Digilocker
4. Github
5. Gpay
6. Paypal
7. Paytm
8. Phonepe
9. Umang
10. Amazon
11. Cred
12. mAadhar
13. Adobe-Acrobat


## Termux Configuration

This installation of termux is for non rooted device as nameless os is not patched with magisk in the production use. We are using termux for:

1. Github and Git
2. Obsidian Git Synchoronization


## Generic System Images (GSI's)

We are testing a new realm of no flashing fun. I am tired of bricking my device in testing and thus in production I guess this would probably be the best choice so far. Also, supported gsi images are under DSU-sideloader github readme.

Below are all that i tested so far in my oneplus 8t:

1. Crdroid V9


## Windows 10 Integration 

### Problem

When i was using my guest devices, 

1. I don't want to install excessive softwares and definitely don't want to store my files on those mechanical hard-drives and thus blocking every way of destroying my data on the guest machine. 
2. I don't want the hassle to move files between windows and android. 
3. I am not able to clone github repos with submodules on windows using github desktop, thus in order to commit to my github repositories i wanted them to store on my android and push them to origin using termux.


### Issues 

These are the previous issues i have faced.

1. Amaze and traditional FTP's were not able to sync dot folders present in storage/emulated/0/
2. Termux SFTP server should be used (windows file explorer doesn't support sftp) GREAT!!!


### Solution

1. Download [WinFsp](https://github.com/winfsp/winfsp) + [SSHFS-WIN](https://github.com/winfsp/sshfs-win) and install it.
2. Start a sshd server on termux
3. Mapping a network drive with this command `\\sshfs\u0_a393@192.168.1.5!8022`


### Caveats? 

Yes, there are issues with this approach. Like, I wasn't been able to access my termux symlinks at all. So i created a folder with my github repositories cloned and then worked on them. This setup just solved one problem of editing my github repositories using VSCode on guest pc. 


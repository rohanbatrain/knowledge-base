## Recovery

We are using OrangeFox Recovery for Evolution-X


## Flashing Evolution-X

Here are the steps that we need to follow in order to flash evolution-x:

* Sideload copy_partition 
```bash
adb sideload copy_partitions.zip
```


* Normal adb sideload command wasn't working, so selected the zip and installed using orangefox.
* Formatted the Data partition, if not done already evolutionx would stuck in bootloop and after rebooting twice it will automatically ask you to wipe your data partition.
* Reboot to new system

## Magisk

Magisk v26.1 is known to fail and doesn't install properly. Issue that i faced was it wasn't able to install itself when magisk manager tries to install itself after flashing. So i tested different versions and the most stable one that i found was [v25.2](https://github.com/topjohnwu/Magisk/releases/download/v25.2/Magisk-v25.2.apk)


### Magisk Modules

These are the modules that i installed on this rom

1. [Bootloop-Saver](https://download.magiskzip.com/download/magisk-bootloop-saver/)
2. [Universal-Safety-Net](https://download.magiskzip.com/download/universal-safetynet-fix-magisk-module/)
3. [Lsposed-Magisk-Module-Zygisk](https://download.magiskzip.com/download/lsposed-magisk-module-zygisk/)
4. [Cloudflaredns4magisk](https://download.magiskzip.com/download/cloudflaredns4magisk/)
5. [Cloudflare-Dns4magisk-IPV6](https://download.magiskzip.com/download/cloudflaredns4magisk-ipv6/)


### Magisk configuration

1. Hide magisk app - renamed to Rohan
2. Enabled zygisk, added systemless hosts, enabled enforce deny list
3. Added Google play services, google play store to denylist, successfully passed Safety-Net.

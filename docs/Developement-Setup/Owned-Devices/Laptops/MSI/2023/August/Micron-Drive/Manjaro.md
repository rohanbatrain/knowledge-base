
## Packages Installed

1. vim 
2. paru
3. tree
4. intel-media-driver
5. digikam
6. veracrypt

## Paru packages

1. vscodium
2. qrcodegencpp (required by obs-studio)
3. obs-studio-git (be sure to use -git instead of obs-studio standalone cause i have faced several dependency error which resulted in segmentation fault and core dump)
4. droidcam
5. droidcam-obs-plugin
6. v4l2loopback-dc
7. parsec-bin
8. anki

## Suggested packages

These are the packages my team mate installed to debug/solve a problem,

1. bluez-utils


## Setup

### File management

Here i would leave notes on how i manage my home directory and their subsequent sub directories.

### Droidcam

After a lot of debugging and trying to install droidcam now i made progress.

* Use the following command in order to know your linux headers

```bash
mhwd-kernel -li
```

* then install it by :

```bash
sudo pacman -S <linux-header name> 
```

#### Failed

After a lot of time spending this linux61 kernel has some issues.

```bash
uname -r 
> 6.1.51-1-MANJARO
```

This particular version wasn't able to install droidccam v412loopback drivers. 


##### Fallback

This is future me from morning now my system takes 1.28 mins unnecesarily to try to load the kernel module which always fails.

Removing the following packages in order to fix it

```bash
sudo pacman -R linux61-headers droidcam
```

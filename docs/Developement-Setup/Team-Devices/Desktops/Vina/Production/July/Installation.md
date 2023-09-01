# Proxmox 

## Installation

### Partition

TOTAL usable space on ssd = 223.58 GiB


filesystem : xfs
hdsize : 220.0
swapsize: 20
maxroot: 20 
minfree: 20
maxvz: NULL


we have left 3 gb of unpartitioned space on our sdd


### Location and Timezone

Country: India
TImezon : Asia/Kolkata
Keyboard Lay: US english


### Installation 

Ready, 3 2 1 Stopwatch

Accurate timing from start to finish is 3mins

### Notes

We have 16gb ram but in idle state proxmox uses around 1.5 so we are hypothetically reserving 4 GB for just this.

#### networking

2 ip for each proxmox installation, why 2? 

Because we have 2 network interfaces, so for ease and clean setup 1 ip consequitively for each network interfaces. calculation => x number of network interfaces then x number of ip is to be configured in seq.




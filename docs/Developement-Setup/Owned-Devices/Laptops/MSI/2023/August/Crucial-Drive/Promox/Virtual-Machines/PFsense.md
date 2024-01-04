## pfsense

We have followed the following blog "pfsense with proxmox" from official site.

### VM Creation

Pretty straight forward setup same which is followed for a freebsd based system. 

```yaml
Graphic Card : Spice 
SCSI Controller : Virtio SCSI single 
Bus/Device : Virtio Block
Disk size : 10g
socket : 1 
core : 1
type : host
memory : 2048
network-model : Virtio paravirtualized
Firewall : unticked
```

### Post creation
Add a second vmbr1 to your pfsense vm. virtio paravirtualized

### Installation on vm

Typical normal installation.

### Configuration

Auto fetch ip on wan from dhcp, go into your router and set a static ip.

`Lan = 11.x.x.1`

In order to setup my interfaces i have gone into vmbr and ticked the disconnect option in order to virtually disconnect the bridge. Then gone into pfsense to autodetect the interface again (reconnect when prompted to do so) in order to give it a static lan and wan ip. 

DHCP is enabled on lan in order to give out ip using vmbr1, so if you have a vm with 2 bridges they are going to receive two up-links (assuming wan is active on pfsense)

```yaml
uplink-1 : 10.x.y.z.a
uplink-2 : 11.x.y.z.a
```

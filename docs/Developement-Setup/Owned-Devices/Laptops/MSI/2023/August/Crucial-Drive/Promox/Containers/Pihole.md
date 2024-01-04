## Pihole 

We used proxmox lxc ubuntu 23.04 template and on top of it installed pihole. 


The steps of creating CT was:

```yaml
hostname: pihole
disk size: 4
Cores: 1
Memory: 1024
swap: 1024
ipv4: static
ipv6: dhcp request
dns domain: pihole.vina.xxxx.xx.x
dns-server: 1.1.1.1
```


### Installing

1. update the system and install curl
2. go to pihole documentation or directly enter a controversial bash snippet w/o verifying :lol:

```bash
curl -sSL <https://install.pi-hole.net> | bash
```

3. give a static ip to pihole container.
4. autostart=true

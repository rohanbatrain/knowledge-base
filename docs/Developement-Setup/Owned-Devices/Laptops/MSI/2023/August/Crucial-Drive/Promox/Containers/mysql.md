## Mysql

We used proxmox lxc ubuntu 23.04 template and on top of it installed mariadb.

The steps of creating CT was:

```yaml
hostname: mysql
memory: 1024
ostype: ubuntu
swap: 1024
ipv4: static
ipv6: dhcp request
dns domain: mysql.vina.xxxx.xx.x
dns-server: 1.1.1.1
```

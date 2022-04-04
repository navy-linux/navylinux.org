---
title : "Proxmox Server"
description: >
    Navy Linux private cloud base on the Proxmox Server.
---

# Virtual hardware platform
Navy Linux Build System hosted on the Proxmox VE as base virtual hardware platform.


## Installation guide Proxmox

[Install Guide](https://pve.proxmox.com/wiki/Install_Proxmox_VE_on_Debian_Buster)
[Network Configuration](https://pve.proxmox.com/wiki/Network_Configuration)

```bash
echo "deb http://download.proxmox.com/debian/pve buster pve-no-subscription" > /etc/apt/sources.list.d/pve-install-repo.list
wget http://download.proxmox.com/debian/proxmox-ve-release-6.x.gpg -O /etc/apt/trusted.gpg.d/proxmox-ve-release-6.x.gpg
chmod +r /etc/apt/trusted.gpg.d/proxmox-ve-release-6.x.gpg  # optional, if you have a non-default umask
apt update && apt full-upgrade
apt install proxmox-ve postfix open-iscsi
apt remove os-prober
```

* Create Users
* Create Linux Bridge
* apt-get install ifupdown2

```bash
auto lo
iface lo inet loopback

auto ens3
iface ens3 inet static
  address 10.39.93.198
  network 10.39.93.0
  netmask 255.255.255.0
  gateway 10.39.93.1

auto vmbr0
iface vmbr0 inet static
 address  172.16.0.1
 netmask  255.255.0.0
 bridge-ports none
 bridge-stp off
 bridge-fd 0

 post-up   echo 1 > /proc/sys/net/ipv4/ip_forward
 post-up   iptables -t nat -A POSTROUTING -s '172.16.0.0/16' -o ens3 -j MASQUERADE
 post-down iptables -t nat -D POSTROUTING -s '172.16.0.0/16' -o ens3 -j MASQUERADE
```


###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/infrastructure/proxmox_server/index.md)
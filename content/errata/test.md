---
title : "Test"
description: >
  Test Description
date: "2021-08-23"
---

# Install / Uninstall Cockpit Web Console in Navy Linux 8

cockpit is not installed by default with minimal release of Navy Linux, and you can install it on your system by using the command below, which will install the cockpit with its required dependencies.

## Install cockpit
Cockpit is a server administration web console, focused on providing a modern-looking and user-friendly interface to manage Navy Linux servers

```bash
yum update -y
yum install cockpit -y
```
##### Enable and start the cockpit.socket

```bash
systemctl start cockpit.socket
systemctl enable --now cockpit.socket
```

##### Web console login

```bash
Localhost: https://localhost:9090
Remotely as server’s IP address: https://<IP-addres-here>:9090
```

## Uninstall cockpit

Uninstall/Remove cockpit from Navy Linux

```bash
systemctl stop cockpit
rpm -e cockpit-system
rpm -e cockpit-bridge
rpm -e cockpit-ws
rm -rf /run/cockpit
rm -rf /etc/cockpit
rm -rf /usr/share/cockpit
rm -rf /var/lib/selinux/targeted/active/modules/100/cockpit
rm -rf /usr/share/selinux/targeted/default/active/modules/100/cockpit
```
### Finished!
Feel free to report any issue on Issue Tracker https://git.navylinux.org/issue-tracker/general/-/issues



###### [Edit this page](https://git.navylinux.org/website/navylinux-org/-/blob/main/content/wiki/cockpit.md)

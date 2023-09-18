---
title: "Maintain CentOS 8 until 2030"
description: >
    Maintain CentOS 8 until 2030, while obtaining the most recent updates from the Navy.

weight: 10
---

# Maintain CentOS 8 until 2030, while obtaining the most recent updates from the Navy. With this approach, you will use CentOS 8 as late as 2030 without changing or migrating OS. 

Here is how to Maintain CentOS 8 until 2030.

#### Backup First

Create a backup of your machine before executing.

##### Remove CentOS repositories

```bash
rm -rf /etc/yum.repos.d/Cent*
```

##### Install Navy Linux gpg-keys

```bash
yum install -y https://cdn.navylinux.org/navylinux/releases/8.5r1/x86_64/os/Packages/navylinux-gpg-keys-8.5r1-121221.noarch.rpm
```

##### Setup Release Variables

```bash
echo "8" > /etc/dnf/vars/releasever
echo "8" > /etc/yum/vars/releasever
echo "8.5r1" > /etc/yum/vars/releaseversion
echo "8.5r1" > /etc/dnf/vars/releaseversion
uname -i > /etc/yum/vars/infra
uname -i > /etc/dnf/vars/infra
```

> Note: `Warning: Only supported on x86_64-based hardware.` 

##### Create repositories

```bash
curl -o /etc/yum.repos.d/navy-linux-base.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-base.repo
curl -o /etc/yum.repos.d/navy-linux-every.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-every.repo
curl -o /etc/yum.repos.d/navy-linux-powertools.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-powertools.repo
curl -o /etc/yum.repos.d/navy-linux-kernel.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-kernel.repo

```

##### Upgrade and patch CentOS 8

```bash
yum clean all
yum update -y
```

# Finished!

Welcome to the Navy Linux Family, feel free to report any issue on Issue Tracker https://github.com/navy-linux/issue-tracker

###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/migrate/maintain-centos-8-until-2030.md)

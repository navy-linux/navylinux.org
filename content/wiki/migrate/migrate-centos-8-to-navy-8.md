---
title : "Migrate a Linux System from CentOS 8.x to Navy Linux 8.5 "
description: >
    Migrating from CentOS 8.x to Navy Linux 8.5

weight: 14
---

# Manually Migrating from CentOS 8 minimal to Navy Linux 8.5 minimal.

Here is how CentOS 8 minimal converted to Navy Linux 8.5 minimal.

#### Backup First

Create a backup of your machine before executing.

##### Install Navy Linux gpg-keys

```bash
yum install -y https://cdn.navylinux.org/navylinux/releases/8.5r1/x86_64/os/Packages/navylinux-gpg-keys-8.5r1-121221.noarch.rpm
```
##### Erase CentOS Release

```bash
rpm --erase --nodeps   $( rpm -qa | egrep 'centos' )
```
##### Create a Backup of all repositories and remove CentOS repositories

```bash
cp -R /etc/yum.repos.d /etc/yum.repos.backup
rm -rf /etc/yum.repos.d/Cent*
```

##### Setup Navy Linux Release Variables

```bash
echo "8" > /etc/dnf/vars/releasever
echo "8" > /etc/yum/vars/releasever
echo "8.5r1" > /etc/yum/vars/releaseversion
echo "8.5r1" > /etc/dnf/vars/releaseversion
uname -i > /etc/yum/vars/infra
uname -i > /etc/dnf/vars/infra
```

##### Create Navy Linux repositories

```bash
curl -o /etc/yum.repos.d/navy-linux-base.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-base.repo
curl -o /etc/yum.repos.d/navy-linux-every.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/main/navy-linux-every.repo
```

##### Upgrade to Navy linux

```bash
yum clean all
yum update -y
```

# Finished!

Welcome to Navy Linux Family, feel free to report any issue on Issue Tracker https://github.com/navy-linux/issue-tracker

###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/migrate/migrate-centos-8-to-navy-8.md)

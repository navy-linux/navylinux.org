---
title : "Migrate a Linux System from CentOS 8.x to Navy Linux 8.4 "
description: >
    Migrating from CentOS 8.x to Navy Linux 8.4

weight: 14
---

# Manually Migrating from CentOS 8 minimal to Navy Linux 8.4 minimal.

Here is how CentOS 8 minimal converted to Navy Linux 8.4 minimal.

#### Backup First

Create a backup of your machine before executing.

##### Install Navy Linux gpg-keys

```bash
yum install -y https://mirror1.navylinux.org/navylinux/releases/8.4/x86_64/os/Packages/navylinux-gpg-keys-8.4-2.noarch.rpm
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
echo "8.4" > /etc/yum/vars/releaseversion
echo "8.4" > /etc/dnf/vars/releaseversion
uname -i  > /etc/yum/vars/infra
uname -i > /etc/dnf/vars/infra
```

##### Create Navy Linux repositories

```bash
curl -o /etc/yum.repos.d/navy-linux-base.repo https://git.navylinux.org/packaging/navylinux-release/-/raw/master/navy-linux-base.repo
curl -o /etc/yum.repos.d/navy-linux-every.repo https://git.navylinux.org/packaging/navylinux-release/-/raw/master/navy-linux-every.repo
```

##### Upgrade to Navy linux

```bash
yum clean all
yum update -y
yum upgrade -y
```

##### Reinstall packages available in the Navy Linux repositories

```bash
yum repository-packages nl-base move-to -y
yum repository-packages nl-every move-to -y
```

# Finished!

Welcome to Navy Linux Famil, feel free to report any issue on Issue Tracker https://git.navylinux.org/issue-tracker/general/-/issues

###### [Edit this page](https://git.navylinux.org/website/navylinux-org/-/blob/main/content/wiki/migrate/migrate-centos-8-to-navy-8.md)

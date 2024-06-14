---
title : "Migrate a Linux System from CentOS 7.x to Navy Linux 7.9r1 "
description: >
    Migrating from CentOS 7.x to Navy Linux 7.9r1

weight: 5
---

# CentOS 7 end of the life support from Navy Linux 7.

Here is how CentOS 7.x converted to Navy Linux 7.9r1.

#### Backup First

Create a backup of your machine before executing.

##### Create a Backup of all repositories and remove CentOS repositories

```bash
cp -R /etc/yum.repos.d /etc/yum.repos.backup
rm -rf /etc/yum.repos.d/Cent*
```

##### Setup Navy Linux Release Variables

```bash
echo "7" > /etc/yum/vars/releasever
echo "7.9r1" > /etc/yum/vars/releaseversion
uname -i > /etc/yum/vars/infra
```

##### Create Navy Linux repositories

```bash
curl -o /etc/yum.repos.d/navy-linux-base.repo https://raw.githubusercontent.com/navy-linux/navylinux-release/7.9r1/navy-linux-base.repo
```

##### Upgrade to Navy linux

```bash
yum clean all
yum update -y
```

# Finished!

Welcome to Navy Linux Family, feel free to report any issue on Issue Tracker https://github.com/navy-linux/issue-tracker

###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/migrate/migrate-centos-7-to-navy-7.md)

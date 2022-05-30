---
title : "Navy Linux 8.6r1 Release Notes"

description: >
    Navy Linux 8.6r1 Release Notes
weight: 20
---
# Navy Linux 8.6r1 Now Available!

Navy Linux 8.6r1 Now Available for Workstations, Servers. The release notes for Navy Linux 8.6r1 contain a summary of the changes made to the Navy Linux base system on the development line.

## Introduction

Navy Linux is a rebuild of the Red Hat Linux project just as the CentOS Linux project has been for all these years. This document contains the release notes for Navy Linux 8.6r1. It describes recently added, changed, or deleted features of EL8. 


## Security Advisories

Advisory to verify CHECKSUM, Download iso and CHECKSUM in same folder and check "md5sum -c CHECKSUM" Link to download https://cdn.navylinux.org/navylinux/releases/8.6r1/x86_64/iso/

Secureboot is missing in this release but packages are secued with the GPG key. 

## Errata Notices

- Remmina added as default remote desktop client for better RDP and SSL session. 
- Firefox 100 added as default browser. 
- Later versions of the following components are now available as new module streams like PHP 8.0 and Perl 5.32
- Compiler toolsets have been updated to GCC Toolset 11

## Installer Images

Navy Installer Images available on all mirrors at path /navylinux/releases/8.6r1/x86_64/iso/ or download from
Download page https://navylinux.org/download/

## Kernel

Navy Linux Kernel Packages available in nl-kernel repo.

## [nl-kernel] - kernel repository

nl-kernel kernel repository allows kernel care and updates for Navy Linux Kernel. Package included in Kernel repository available at https://cdn.navylinux.org/navylinux/releases/8.6r1/x86_64/kernel/Packages/

## [nl-base] - BaseOS repository

OS repository group of Minimal OS and Server packages. https://cdn.navylinux.org/navylinux/releases/8.6r1/x86_64/os/

## [nl-powertools] - Powertools repository

Powertools packages hosted at nl-powertools https://cdn.navylinux.org/navylinux/releases/8.6r1/x86_64/powertools/ 

## EPEL Installation

Some EPEL packages depend on the Powertools repository, enable repo and install Extra Packages for Enterprise Linux (EPEL)

```bash
dnf config-manager --set-enabled nl-powertools
dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
```

## Hardware Support

Arch x86_64 supported Hardware for the Navy Linux Release 8.6r1

## Minimum Hardware requirement for production deployment

CPU:  2 cores

RAM:  4 GB

## Virtualization Hypervisors

Virtualization Hypervisors have the following hardware requirements:

- A CPU with the hardware virtualization extension
- An Intel® 64 extension

## Packaging Changes

Defualt Upgrade is locked and available soon, to quick upgrade from Navy Linux 8.5r1 to 8.6r1 follow as 

```bash
echo "8.6r1" > /etc/dnf/vars/releaseversion
dnf update
```


###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/release-note-8.6r1.md)

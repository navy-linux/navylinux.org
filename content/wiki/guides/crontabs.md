---
title : "Crontab to Automate Tasks on Navy Linux"
description: >
    Install Crontab to Automate Tasks on Navy Linux
tags:
    - crontab   
---

# Install Crontab to Automate Tasks on Navy Linux

Crontab is a time-based job scheduling daemon. Follow this guide, recommended a non-root user with administrative privileges configured, but these commands test under root.

##### Before installing cron on a Navy Linux, update packages

```bash
yum update -y
```
#####  Install the crontab package


```bash
yum install crontabs -y
```
##### Enable the crond service at boot

```bash
systemctl enable crond.service
```
##### start the crond service

```bash
systemctl start crond.service
```
##### Crontab Examples

How to write a crontab schedule expression for Linux
[examples available here external link](https://crontab.guru/examples.html)

# Finished!

Feel free to report any issue on Issue Tracker https://github.com/navy-linux/issue-tracker

###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/guides/crontabs.md)

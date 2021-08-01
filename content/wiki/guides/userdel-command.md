---
title : "Delete/Remove Users in Navy Linux (userdel Command) "
description: >
    Delete/Remove Users in Navy Linux (userdel Command)
tags:
    - userdel    
---

# Delete/Remove Users in Navy Linux (userdel Command)

Guide to delete a user account and all its associated files using the userdel command.

#### Backup First

Create a backup before executing.

##### userdel Command Syntax

```bash
userdel [OPTIONS] USERNAME
```
##### Kill all jobs of user before to delete

```bash
killall -u  USERNAME
```
#####  Delete User

when removing a user account with userdel, the user home and mail spool directories are not removed.

```bash
killall -u  USERNAME
```
#####  Delete User and also remove home and mail spool directories

Use the -r  option to force userdel to remove the user’s home directory and mail spool

```bash
killall -r  USERNAME
```
##### Forcefully delete a user

```bash
killall -f  USERNAME
```

# Finished!

Feel free to report any issue on Issue Tracker https://git.navylinux.org/issue-tracker/general/-/issues

###### [Edit this page](https://git.navylinux.org/website/navylinux-org/-/blob/main/content/wiki/guides/userdel-command.md)

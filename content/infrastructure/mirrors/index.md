---
title : "Become a Mirror"
description: >
    Navy Linux Mirroring guide, how to become a public mirror.
---

# How to Become a Navy Linux Mirror

#### The only requirements for becoming a mirror are:

1- A willingness to mirror The Navy Linux.

2- Mirroring is done using rsync over SSH, it requires public SSH key file, submit to The Navy Linux infra Team.

3- Only HTTPS mirror should be utilized (HTTP and FTP mirrors are not accepted)

4- Available bandwidth and disk space, Each release of Navy Linux takes about 60GB of disk space for all of the various packages we create.

5- We recommend our mirrors have at least a 100Mbit/sec connection to the Internet

6- The ability to do directory listings on mirrored sub-directories on your mirror Server.

7- The mirror should update itself, preferably every 12 hours, but at the very least, once a day.

## Required info.

- Name of the Organization:
- Mirror Public URL:
- Mirror Public IP address:
- Mirror Maintainer Name:
- Mirror Maintainer email:
- Mirror Maintainer contact no:
- user public ssh key file in (ssh-rsa) formate:
- Internet connection speed:


##### Drop us an email with the above details to team@navylinux.org

# rsync Information

### The rsync over SSH URL for mirror:

```bash
mirror.navylinux.org
```
### Here is the suggested rsync command for a mirror to use:

```bash
# rsync over ssh suggested command
rsync --bwlimit=5000 -arvz -e 'ssh -p <port>' --progress --delete  secure@mirror.navylinux.org:/mirror/ /path/to/local/download/
# <port> is private port you can receive details when your request is approved
```

# Getting Added to the Mirror List
After completing these above steps, Once you have initially mirrored The Navy Linux, reaply us on the same email thread. We can review and publish your mirror url on the mirrorlist.

###### Still have any question to setting up the mirror, please feel free to share with us over email at team@navylinux.org


###### [Edit this page](https://git.navylinux.org/website/navylinux-org/-/tree/main/content/infrastructure/mirrors/index.md)
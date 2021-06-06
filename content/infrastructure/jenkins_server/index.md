---
title : "Jenkins Server"
description: >
    Navy Linux Build platform for RPM build pipeline.
---

# Jenkins Server

## Install Guide
[Install Guide](https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos)

```bash
wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum upgrade
yum install jenkins java-1.8.0-openjdk-devel
systemctl daemon-reload
systemctl start jenkins

YOURPORT=8080
PERM="--permanent"
SERV="$PERM --service=jenkins"

firewall-cmd $PERM --new-service=jenkins
firewall-cmd $SERV --set-short="Jenkins ports"
firewall-cmd $SERV --set-description="Jenkins port exceptions"
firewall-cmd $SERV --add-port=$YOURPORT/tcp
firewall-cmd $PERM --add-service=jenkins
firewall-cmd --zone=public --add-service=http --permanent
firewall-cmd --reload
```

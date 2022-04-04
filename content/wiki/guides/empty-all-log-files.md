---
title : "Empty all log files in log directory"
description: >
    Empty all log files in log director
tags:
    - Empty all log files in log director  
---

# Empty all log files in log directory

Guide to Empty all log files in log directory

##### Empty all log files using for loop

```bash
for log in /var/log/*; do
     test -f "$log" && > "$log"
done
```


# Finished!

Feel free to report any issue on Issue Tracker https://github.com/navy-linux/issue-tracker

###### [Edit this page](https://github.com/navy-linux/navylinux.org/blob/main/content/wiki/guides/empty-all-log-files.md)

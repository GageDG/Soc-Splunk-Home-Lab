# Splunk Disk Space Error

## Issue

After running the Splunk web server the following message occured and woulnd't allow us to view any information.
<img width="1915" height="502" alt="SplunkSizeError" src="https://github.com/user-attachments/assets/e50f63a0-3cf4-4f72-9587-b28ff609778e" />

Search not executed: The minimum free disk space (5000MB) reached for /opt/splunk/var/run/splunk/dispatch

## Cause

The Ubuntu VM wasn't allocated enough storage during creation which led to splunk now having enough storage to operate.

## Resolution

Changed the VM's storage allocation from 40G to 80G in the VM settings preventing any further issues.
The logical volume wasthen expanded to use the remaining free space in the volume group.

Commands used:

sudo vgdisplay
sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
sudo resize2fs /dev/ubuntu-vg/ubuntu-lv

After expanding the filesystem, sufficient disk space was available and Splunk resumed executing searches normally.

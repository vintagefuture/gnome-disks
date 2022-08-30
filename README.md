# Getting error gdbus-error-quark 4 while using gnome disks benchmark on microsd card

Thw following command is a workaround for people who do not want to disable SELinux altogether, yet want to use `gnome-disks` on MMC block devices (i.e. `/dev/mmcblk0`):

1. Insert MMC into drive.
2. Execute:

```
chcon -t fixed_disk_device_t /dev/mmcblk0
```

3. Open gnome-disks to run a benchmark on /dev/mmcblk0

Source https://bugzilla.redhat.com/show_bug.cgi?id=1414539

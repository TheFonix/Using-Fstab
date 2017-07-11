# using-Fstab

Start by grabbing the UUID and Filesystem of a mount point:
`blkid /dev/YourDiskID`

This should output some data such as 
```
/dev/vdb: UUID="3038da43-4acf-42f6-86fc-681ec353913d" TYPE="ext4"
```
Then head over to `/etc/fstab` and at the bottom of the file you want to input your new disk, for for exmaple if our output was this
```
/dev/vdb: UUID="3038da43-4acf-42f6-86fc-681ec353913d" TYPE="ext4"
```
we would want to payout our fstab line like this
```
UUID=3038da43-4acf-42f6-86fc-681ec353913d /mnt            ext4    noatime,nodiratime,errors=remount-ro 0 0
```
This would mount the device to the /mnt directory

## Extra Flags?
The `noatime` and `nodiratime` and performance benefits for system during the mount process

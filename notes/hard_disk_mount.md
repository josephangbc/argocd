### Hard Disk Mounts

#### 1. Check name of hard disk mount
```
lsblk
```
Example outputs
```
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda           8:0    0  1.8T  0 disk 
```

#### 2. Mount hard disk to pi directory
```
sudo mount /dev/sda /mnt/extstorage
```
`lsblk` again will state the `MOUNTPOINT`
```
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda           8:0    0  1.8T  0 disk /mnt/extstorage
```
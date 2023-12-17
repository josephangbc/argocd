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


### Automatically Mount Hard Disk using uuid

#### 1. Check uuid of hard disk mount
```
sudo blkid
```
Example outputs
```
/dev/mmcblk0p1: LABEL_FATBOOT="bootfs" LABEL="bootfs" UUID="5DF9-E225" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="14156ac4-01"
/dev/mmcblk0p2: LABEL="rootfs" UUID="3b614a3f-4a65-4480-876a-8a998e01ac9b" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="14156ac4-02"
/dev/sda: UUID="3a9cc070-d64d-45ad-b522-67387fa6bfe3" BLOCK_SIZE="4096" TYPE="xfs"
```

#### 2. Update fstab file
```
sudo vim /etc/fstab
```
```
UUID=3a9cc070-d64d-45ad-b522-67387fa6bfe  /mnt/extstorage  xfs  defaults,nofail  0  2
```

#### 3. verify
```
sudo findmnt --verify --verbose
```

#### 4. reboot
```
sudo reboot
```


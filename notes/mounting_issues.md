### Trigger Mount after editing `/etc/fstab`
```
sudo mount -a
```

### Trigger Export after editing `/etc/exports`
```
sudo exportfs -ra
```
#### Check
```
sudo showmount -e 192.168.18.41
```


### xfs_repair
```
sudo xfs_repair -L /dev/sda

sudo fuser -m /mnt/xfs_mount_point
```
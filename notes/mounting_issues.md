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
sudo showmount -e 192.168.18.47
```
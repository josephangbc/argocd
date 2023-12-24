### NFS Mounts

#### Creating
1. Install NFS Server Packages
```
sudo apt-get update
sudo apt install nfs-kernel-server
```

2. Make Directory to Shared
```
sudo mkdir /mnt/nfs
```

3. Set Permissions
```
sudo chmod 777 /mnt/nfs #everyone can modify files
```

4. Edit `/etc/exports` file
```
/mnt/nfs 192.168.18.0/24(rw,sync,no_subtree_check)
```

5. Make Directory available
```
sudo exportfs -a #making the file share available

sudo systemctl restart nfs-kernel-server #restarting the NFS kernel
```

### Mounting

1. Install NFS Packages
```
sudo apt update
sudo apt install nfs-common
```

2. Mount
```
sudo mkdir /mnt/nfs
sudo mount -t nfs 192.168.18.47:/mnt/nfs /mnt/nfs
```

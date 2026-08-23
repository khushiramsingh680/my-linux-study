## Disk Management 

- [ ] How to check attached disk ?
```yaml
lsblk
fdisk -l
```
-  [ ]  Check disk file size ?
```yaml
df -h
```
- [ ] check the file size
```sh
du -sh <filename>
```
- [ ] How to increase disk size on AWS cloud ?
- [ ] First increase from UI
```sh
sudo growpart /dev/nvme0n1 1
```

- [ ]  How to add a new disk
### your ec2 instance and your volume should be in the same AZ

- [ ]  Format your newly added disk
```sh
vi /etc/fstab

```sh
mkfs.ext4 /dev/nvme1n1
```
- [ ] Mount this to a directory
```sh
mkdir /data
mount /dev/nvme1n1  /data
```
- [ ] now verify using `df -h`
- [ ] Mount it permanent now
```sh
vi /etc/fstab
```
<img width="968" height="178" alt="image" src="https://github.com/user-attachments/assets/a65e6a95-3c0d-4041-b2c7-88be26466665" />

- [ ] How to check uuid of a disk
```sh
blkid
```

#### Using disk as a Swap memory
- [ ] Attach a  disk
- [ ] Format the disk
```sh
mkswap /dev/nvme2n1
```

-  [ ]  How to mount a volume from one instance to another
```sh
mount -o nouuid  /dev/nvme1n1p1 /mnt
```
- [ ] Now you have your dtat in `/mnt`
- [ ] modify `/mnt/etc/fstab`

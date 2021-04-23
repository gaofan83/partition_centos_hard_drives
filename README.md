# Partition Centos hard drives
#####
##### Partition CentOS hard drives (16x12TB) with mdadm  (raid5) 
```
su as root 
mdadm --create /dev/md/md_raid5 --level=5 --raid-devices=16 /dev/sdb2 /dev/sdc2 /dev/sdd2 /dev/sde2 /dev/sdf2 /dev/sdg2 /dev/sdh2 /dev/sdi2 /dev/sdj2 /dev/sdk2 /dev/sdl2 /dev/sdm2 /dev/sdn2 /dev/sdo2 /dev/sdp2 /dev/sdq2  
mkfs.ext4 /dev/md/md_raid5 
mount -t ext4 /dev/md/md_raid5 /home 
vi /etc/fstab 
/dev/md/md_raid5    /home    ext4    defaults    0 0 
```

##### Generate new account from root 
```
sudo adduser username 
sudo passwd username 
sudo mkdir /home/username 
sudo chown username /home/username 
```


- [ ] switch to root user from vagrant
```sh
sudo -s
```

## User & Group
- [ ] Check current user
```sh
whoami
users
w
who
```
- [ ] Last logged in users
```sh
last

lasb
```
- [ ] How to switch from one user to another
```sh
su <username>    user will not have his home directory , exising home directory will be used

su - <user>

```
- [ ] Create a user
```sh
useradd <username>
passwd <username>
```
- [ ] How to create a group
```sh
groupadd <grpname>
```

- [ ] Check all users
```sh
vipw

vi /etc/passwd

or cat /etc/passwd
```

-  [ ] check all group
```sh
vigr
cat /etc/groups
```
- [ ] How to check a user group
```sh
groups groupname
```

## Permission
- Read  r  4
- Write  w  2
- Exexute  x 1
## Permissions are given to:
- users
- groups
- others

- [ ] How to check permission of a file
      
```yaml

-rw-  r-- r--
user         group     Rest of all

-rw-r--r--. 1 root root 0 Aug 11 13:08 justcheck
ls -l
-rw-r--r--. 1 root root 0 Aug 11 13:08 justcheck
```
- [ ] Default permission of a file
```sh
644
```
- [ ] Default permission of a dirctory
```sh
755
```
- [ ] How to change owner of a file/dir
```sh
chown <username> filename/dir
```
- [ ] How to change group of a file/dir
```sh
chgrp <grpname> file/dir
```
- [ ] How to change the permission of a file or dir
```sh
chmod 755 file/dir
```
- [ ] How to Generate a ssh key
```sh
ssh-keygen -f <sshkeyname>
enter
enter
```
- [ ] Where to copy ssh public key
```sh
open pub key
copy contents and paste content to user /home/<user/.ssh/authorized_keys
```

## Permission for a ssh public key 
```sh
chown test01:test01 /home/test01
chown -R test01:test01 /home/test01/.ssh

chmod 755 /home/test01
chmod 700 /home/test01/.ssh
chmod 600 /home/test01/.ssh/authorized_keys
```



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
group groupname
```

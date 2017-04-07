
# Challenge Setup

# List the cloud provider you are using (AWS, GCE, Azure, other)

```
AWS
```
# List the nodes you are using by IP address and name

```
[root@ip-172-31-29-83 ~]# cat /etc/hosts
172.31.29.83 ip-172-31-29-83.ec2.internal ip-172-31-29-83
172.31.17.118 ip-172-31-17-118.ec2.internal ip-172-31-17-118
172.31.16.82 ip-172-31-16-82.ec2.internal ip-172-31-16-82
1172.31.29.66 ip-172-31-29-66.ec2.internal ip-172-31-29-66
127.0.0.1 localhost.localdomain localhost
::1 localhost6.localdomain6 localhost6
[root@ip-172-31-29-83 ~]#

```
# List the Linux release you are using
```
[centos@ip-172-31-29-83 ~]$ cat /etc/centos-release
CentOS Linux release 7.2.1511 (Core)
[centos@ip-172-31-29-83 ~]$

```
# Demonstrate the disk capacity available on each node is >= 30 GB

```
[centos@ip-172-31-29-83 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       80G  877M   80G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000
[centos@ip-172-31-29-83 ~]$

```
# List the command and output for yum repolist enabled

```
cat > /etc/yum.repos.d/MariaDB.repo <<EOF
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.1/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
EOF

```

```
yum install wget

```
```
cd /etc/yum.repos.d/ && wget -c https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo 
```
```
cd ~
```


# Add the following Linux accounts to all nodes 


User neymar with a UID of 2010
User ronaldo with a UID of 2016
Create the group barca and add ronaldo to it
Create the group merengues and add neymar to it

```
useradd -u 2010 neymar
useradd -u 2016 ronaldo

groupadd -g 2026 barca
usermod -G barca ronaldo

groupadd -g 2020 merengues
usermod -G merengues neymar

```

# List the /etc/passwd entries for neymar and ronaldo

```
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
avahi-autoipd:x:170:170:Avahi IPv4LL Stack:/var/lib/avahi-autoipd:/sbin/nologin
systemd-bus-proxy:x:999:997:systemd Bus Proxy:/:/sbin/nologin
systemd-network:x:998:996:systemd Network Management:/:/sbin/nologin
dbus:x:81:81:System message bus:/:/sbin/nologin
polkitd:x:997:995:User for polkitd:/:/sbin/nologin
rpc:x:32:32:Rpcbind Daemon:/var/lib/rpcbind:/sbin/nologin
tss:x:59:59:Account used by the trousers package to sandbox the tcsd daemon:/dev/null:/sbin/nologin
rpcuser:x:29:29:RPC Service User:/var/lib/nfs:/sbin/nologin
nfsnobody:x:65534:65534:Anonymous NFS User:/var/lib/nfs:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
chrony:x:996:993::/var/lib/chrony:/sbin/nologin
centos:x:1000:1000:Cloud User:/home/centos:/bin/bash
neymar:x:2010:2010::/home/neymar:/bin/bash
ronaldo:x:2016:2016::/home/ronaldo:/bin/bash

```

# List the /etc/group entries for barca and merengues

```
[root@ip-172-31-29-83 yum.repos.d]# vi /etc/group
mail:x:12:postfix
man:x:15:
dialout:x:18:
floppy:x:19:
games:x:20:
tape:x:30:
video:x:39:
ftp:x:50:
lock:x:54:
audio:x:63:
nobody:x:99:
users:x:100:
utmp:x:22:
utempter:x:35:
ssh_keys:x:999:
avahi-autoipd:x:170:
input:x:998:
systemd-journal:x:190:centos
systemd-bus-proxy:x:997:
systemd-network:x:996:
dbus:x:81:
polkitd:x:995:
rpc:x:32:
dip:x:40:
tss:x:59:
cgred:x:994:
rpcuser:x:29:
nfsnobody:x:65534:
postdrop:x:90:
postfix:x:89:
sshd:x:74:
chrony:x:993:
centos:x:1000:
neymar:x:2010:
ronaldo:x:2016:
barca:x:2026:ronaldo
merengues:x:2020:neymar

```

# Challenge 1: Install a MySQL server

# Create the Issue Install MySQL or Install MariaDB as appropriate

Use the appropriate YUM repository to install the package.

```
yum update && yum install wget unzip ntp vim bind-utils nscd ntpd MariaDB-server MariaDB-client oracle-j2sdk1.7 cloudera-manager-daemons cloudera-manager-server openldap-clients krb5-libs krb5-workstation -y

```
```
cat > /etc/my.cnf <<EOF
#
# This group is read both both by the client and the server
# use it for options that affect everything
#
[client-server]

#
# include all files from the config directory
#
!includedir /etc/my.cnf.d

[mariadb]
server-id=1
bind-address=0.0.0.0
log-bin=mariadb-bin
binlog-format=ROW
EOF
```

# Install the appropriate DB client package and JDBC connector jar

```

wget -c https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.41.tar.gz && tar zxvf mysql-connector-java-5.1.41.tar.gz && mkdir /usr/share/java && cp mysql-connector-java-5.1.41/mysql-connector-java-5.1.41-bin.jar /usr/share/java/mysql-connector-java.jar

```

# Challenge 2: Install Cloudera Manager 5.9.x








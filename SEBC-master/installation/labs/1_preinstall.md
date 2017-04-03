## 1 Preinstall 

# 1 Check vm.swappiness on all your nodes

'cat /proc/sys/vm/swappiness'
10

# 2 Show the mount attributes of your volume(s)

'df -h'


[root@ip-172-31-19-33 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.8G  2.3G  5.2G  31% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
/dev/xvdf1       37G   48M   37G   1% /data/1
/dev/xvdg1       37G   48M   37G   1% /data/2
[root@ip-172-31-19-33 ~]#


# 3 If you have ext-based volumes, list the reserve space setting

df -h

[root@ip-172-31-19-33 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       7.8G  2.3G  5.2G  31% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
/dev/xvdf1       37G   48M   37G   1% /data/1
/dev/xvdg1       37G   48M   37G   1% /data/2
[root@ip-172-31-19-33 ~]#


# 4 Disable transparent hugepage support

'cat /boot//grub/grub.conf'

[root@ip-172-31-19-33 ~]# cat /boot//grub/grub.conf
default=0
timeout=1

title CentOS (2.6.32-642.15.1.el6.x86_64)
        root (hd0)
        kernel /boot/vmlinuz-2.6.32-642.15.1.el6.x86_64 root=LABEL=centos_root ro crashkernel=auto LANG=en_US.UTF-8 KEYTABLE=us transparent_hugepage=never
        initrd /boot/initramfs-2.6.32-642.15.1.el6.x86_64.img
title CentOS-6.5-x86_64-GA-03 2.6.32-431.el6.x86_64
        root (hd0)
        kernel /boot/vmlinuz-2.6.32-431.el6.x86_64 root=LABEL=centos_root ro transparent_hugepage=never
        initrd /boot/initramfs-2.6.32-431.el6.x86_64.img
	

# 5 List your network interface configuration

'ip addr'

[root@ip-172-31-19-33 ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:9d:6b:be:b1:58 brd ff:ff:ff:ff:ff:ff
    inet 172.31.19.33/20 brd 172.31.31.255 scope global eth0
    inet6 fe80::89d:6bff:febe:b158/64 scope link
       valid_lft forever preferred_lft forever
[root@ip-172-31-19-33 ~]#

# 6 Show correct forward and reverse host lookups
## For /etc/hosts, use getent

'getent hosts ec2-54-91-121-127.compute-1.amazonaws.com'

[root@ip-172-31-19-33 ~]# getent hosts ec2-54-91-121-127.compute-1.amazonaws.com
172.31.19.33    ec2-54-91-121-127.compute-1.amazonaws.com

##For DNS, use nslookup

'nslookup ec2-54-164-164-213.compute-1.amazonaws.com'

[root@ip-172-31-19-33 ~]# nslookup ec2-54-164-164-213.compute-1.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-54-164-164-213.compute-1.amazonaws.com
Address: 172.31.31.194

# 6 Show the nscd service is running

'service nscd status'

[root@ip-172-31-19-33 ~]# service nscd status
nscd (pid 1004) is running...

# 7 Show the ntpd service is  

'service ntpd status'

[root@ip-172-31-19-33 ~]# service ntpd status
ntpd (pid  1042) is running...

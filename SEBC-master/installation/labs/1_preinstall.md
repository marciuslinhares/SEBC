## 1 Preinstall 

# 1 Check vm.swappiness on all your nodes

`cat /proc/sys/vm/swappiness`
10

# 2 Show the mount attributes of your volume(s)

`df -h`

```
[root@ip-172-31-26-86 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       40G  3.6G   37G   9% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
/dev/xvdb        37G   49M   35G   1% /mnt
tmpfs           1.5G     0  1.5G   0% /run/user/1000
[root@ip-172-31-26-86 ~]#

```

# 3 If you have ext-based volumes, list the reserve space setting

`df -h`

```
[root@ip-172-31-26-86 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       40G  3.6G   37G   9% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
/dev/xvdb        37G   49M   35G   1% /mnt
tmpfs           1.5G     0  1.5G   0% /run/user/1000
[root@ip-172-31-26-86 ~]#
```


# 4 Disable transparent hugepage support

`cat /boot/grub/grub.conf`

```
[root@ip-172-31-26-86 ~]# cat /boot/grub/grub.conf
default=0
timeout=0


title CentOS Linux (3.10.0-514.10.2.el7.x86_64) 7 (Core)
        root (hd0)
        kernel /boot/vmlinuz-3.10.0-514.10.2.el7.x86_64 ro root=UUID=ef6ba050-6cdc-416a-9380-c14304d0d206 console=hvc0 LANG=en_US.UTF-8 transparent_hugepage=never
        initrd /boot/initramfs-3.10.0-514.10.2.el7.x86_64.img
title CentOS Linux 7 (3.10.0-327.10.1.el7.x86_64)
        root (hd0)
        kernel /boot/vmlinuz-3.10.0-327.10.1.el7.x86_64 ro root=UUID=ef6ba050-6cdc-416a-9380-c14304d0d206 console=hvc0 LANG=en_US.UTF-8 transparent_hugepage=never
        initrd /boot/initramfs-3.10.0-327.10.1.el7.x86_64.img
[root@ip-172-31-26-86 ~]#

```

# 5 List your network interface configuration

`ip addr`

```
[root@ip-172-31-26-86 ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:28:bb:41:b7:c4 brd ff:ff:ff:ff:ff:ff
    inet 172.31.26.86/20 brd 172.31.31.255 scope global dynamic eth0
       valid_lft 2395sec preferred_lft 2395sec
    inet6 fe80::828:bbff:fe41:b7c4/64 scope link
       valid_lft forever preferred_lft forever
[root@ip-172-31-26-86 ~]#

```
# 6 Show correct forward and reverse host lookups
## For /etc/hosts, use getent

`getent hosts ec2-54-147-224-170.compute-1.amazonaws.com`

```
[root@ip-172-31-26-86 ~]# getent hosts ec2-54-147-224-170.compute-1.amazonaws.com
172.31.24.88    ec2-54-147-224-170.compute-1.amazonaws.com
[root@ip-172-31-26-86 ~]#

```

## For DNS, use nslookup

`nslookup ec2-54-204-94-159.compute-1.amazonaws.com`

```
[root@ip-172-31-24-88 ~]# nslookup ec2-54-204-94-159.compute-1.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-54-204-94-159.compute-1.amazonaws.com
Address: 172.31.17.210

```
# 6 Show the nscd service is running

`service nscd status`

```
[root@ip-172-31-26-86 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
? nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-04-04 00:09:59 UTC; 25min ago
  Process: 496 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 497 (nscd)
   CGroup: /system.slice/nscd.service
           +-497 /usr/sbin/nscd

Apr 04 00:09:58 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitoring directory `/etc` (2)
Apr 04 00:09:58 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitoring file `/etc/services` (6)
Apr 04 00:09:58 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitoring directory `/etc` (2)
Apr 04 00:09:58 ip-172-31-26-86.ec2.internal nscd[497]: 497 disabled inotify-based monitoring for file `/etc/netgroup': No such file or...ectory
Apr 04 00:09:58 ip-172-31-26-86.ec2.internal nscd[497]: 497 stat failed for file `/etc/netgroup'; will try again later: No such file or...ectory
Apr 04 00:09:59 ip-172-31-26-86.ec2.internal systemd[1]: Started Name Service Cache Daemon.
Apr 04 00:10:01 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitored file `/etc/resolv.conf` was written to
Apr 04 00:10:01 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitoring file `/etc/resolv.conf` (5)
Apr 04 00:10:01 ip-172-31-26-86.ec2.internal nscd[497]: 497 monitoring directory `/etc` (2)
Apr 04 00:10:18 ip-172-31-26-86.ec2.internal nscd[497]: 497 checking for monitored file `/etc/netgroup': No such file or directory
Hint: Some lines were ellipsized, use -l to show in full.
[root@ip-172-31-26-86 ~]#

```
# 7 Show the ntpd service is  

`service ntpd status`

```
[root@ip-172-31-26-86 ~]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
? ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-04-04 00:38:31 UTC; 1min 29s ago
  Process: 9178 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9179 (ntpd)
   CGroup: /system.slice/ntpd.service
           +-9179 /usr/sbin/ntpd -u ntp:ntp -g

Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listen and drop on 1 v6wildcard :: UDP 123
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listen normally on 2 lo 127.0.0.1 UDP 123
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listen normally on 3 eth0 172.31.26.86 UDP 123
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listen normally on 4 lo ::1 UDP 123
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listen normally on 5 eth0 fe80::828:bbff:fe41:b7c4 UDP 123
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: Listening on routing socket on fd #22 for interface updates
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal systemd[1]: Started Network Time Service.
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: 0.0.0.0 c016 06 restart
Apr 04 00:38:31 ip-172-31-26-86.ec2.internal ntpd[9179]: 0.0.0.0 c012 02 freq_set kernel 14.141 PPM
Apr 04 00:38:38 ip-172-31-26-86.ec2.internal ntpd[9179]: 0.0.0.0 c615 05 clock_sync
[root@ip-172-31-26-86 ~]#

```



```
!includedir /etc/my.cnf.d

[mariadb]
server-id=1
bind-address=0.0.0.0
log-bin=mariadb-bin
binlog-format=ROW
EOF
```

```
yum update && yum install wget unzip ntp vim bind-utils nscd ntpd MariaDB-server MariaDB-client oracle-j2sdk1.7 cloudera-manager-daemons cloudera-manager-server openldap-clients krb5-libs krb5-workstation -y
```


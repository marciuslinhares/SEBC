
# repository
```
yum install wget

cd /etc/yum.repos.d/ && wget -c https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo 
cd ~
```
# List repositories
```
[root@ip-172-31-29-83 ~]# ls /etc/yum.repos.d/
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo    CentOS-Vault.repo      MariaDB.repo
CentOS-CR.repo    CentOS-fasttrack.repo  CentOS-Sources.repo  cloudera-manager.repo
[root@ip-172-31-29-83 ~]#

```
# Install CM
```
yum update && yum install wget unzip ntp vim bind-utils nscd ntpd MariaDB-server MariaDB-client oracle-j2sdk1.7 cloudera-manager-daemons cloudera-manager-server openldap-clients krb5-libs krb5-workstation -y

```


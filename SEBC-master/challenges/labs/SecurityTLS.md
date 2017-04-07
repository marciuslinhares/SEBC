# Create Keys

```
keytool -genkeypair -alias clouderamanager -keyalg RSA -keysize 2048 -dname "cn=$(hostname -f), ou=IT, o=CLOUDERA, l=Brasilia, st=DF, c=BR" -keypass 12345678 -keystore $(hostname -f).jks -storepass 12345678 -validity 365

ls

rm -rf $JAVA_HOME/jre/lib/security/jssecacerts

cp $JAVA_HOME/jre/lib/security/cacerts $JAVA_HOME/jre/lib/security/jssecacerts

keytool -export -alias clouderamanager -keystore $(hostname -f).jks -rfc -file cm-selfsigned.cer -storepass 12345678

ls

cp /opt/cloudera/security/cm-selfsigned.cer /opt/cloudera/security/x509/$(hostname -f).pem

ls

keytool -import -alias clouderamanager -file /opt/cloudera/security/cm-selfsigned.cer -keystore $JAVA_HOME/jre/lib/security/jssecacerts -storepass changeit

```
systemctl restart cloudera-scm-server

keytool -list -v -keystore ${hostname -f}.jks -alias clouderamanager

chown cloudera-scm:cloudera-scm -R /usr/java/jdk1.7.0_67-cloudera/jre/lib/security/jssecacerts


# 

/etc/cloudera-scm-agent/config.ini

```
[root@ip-172-31-22-23 ~]# cat /etc/cloudera-scm-agent/config.ini | grep tls
use_tls=1
[root@ip-172-31-22-23 ~]#

```





===== CentOS 5.x | RHEL 5.x | Oracle Linux 5.x =====

service nrpe stop
chkconfig nrpe off
rm -f /etc/init.d/nrpe => mv /etc/init.d/nrpe /etc/init.d/nrpe.OLD


yum --disablerepo=* install nagios-common-4.4.3-3.el6.x86_64.rpm
Loaded plugins: product-id, security, subscription-manager
Updating certificate-based repositories.
Unable to read consumer identity
Setting up Install Process
Examining nagios-common-4.4.3-3.el6.x86_64.rpm: nagios-common-4.4.3-3.el6.x86_64
Marking nagios-common-4.4.3-3.el6.x86_64.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package nagios-common.x86_64 0:4.4.3-3.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================================================================================================================================================
 Package                                        Arch                                    Version                                       Repository                                                          Size
===============================================================================================================================================================================================================
Installing:
 nagios-common                                  x86_64                                  4.4.3-3.el6                                   /nagios-common-4.4.3-3.el6.x86_64                                  0.0

Transaction Summary
===============================================================================================================================================================================================================
Install       1 Package(s)

Installed size: 0
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
Warning: RPMDB altered outside of yum.
  Installing : nagios-common-4.4.3-3.el6.x86_64                                                                                                                                                            1/1
Installed products updated.
  Verifying  : nagios-common-4.4.3-3.el6.x86_64                                                                                                                                                            1/1

Installed:
  nagios-common.x86_64 0:4.4.3-3.el6

Complete!



 yum --disablerepo=* install nrpe-3.2.1-6.el6.x86_64.rpm
Loaded plugins: product-id, security, subscription-manager
Updating certificate-based repositories.
Unable to read consumer identity
Setting up Install Process
Examining nrpe-3.2.1-6.el6.x86_64.rpm: nrpe-3.2.1-6.el6.x86_64
Marking nrpe-3.2.1-6.el6.x86_64.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package nrpe.x86_64 0:3.2.1-6.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================================================================================================================================================
 Package                                   Arch                                        Version                                             Repository                                                     Size
===============================================================================================================================================================================================================
Installing:
 nrpe                                      x86_64                                      3.2.1-6.el6                                         /nrpe-3.2.1-6.el6.x86_64                                      358 k

Transaction Summary
===============================================================================================================================================================================================================
Install       1 Package(s)

Total size: 358 k
Installed size: 358 k
Is this ok [y/N]: y
Downloading Packages:
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : nrpe-3.2.1-6.el6.x86_64                                                                                                                                                                     1/1
Installed products updated.
  Verifying  : nrpe-3.2.1-6.el6.x86_64                                                                                                                                                                     1/1

Installed:
  nrpe.x86_64 0:3.2.1-6.el6

Complete!


service nrpe status
Checking for nrpe daemon...nrpe is stopped

 nrpe -V
NRPE - Nagios Remote Plugin Executor
Version: 3.2.1

chkconfig nrpe on
chkconfig --list |grep nrpe
nrpe            0:off   1:off   2:on    3:on    4:on    5:on    6:off



copiare file nrpe.cfg in  /etc/nagios/
copiare file commands.cfg in /etc/nrpe.d/

mkdir /usr/lib64/nagios/libexec
cp /usr/local/nagios/libexec/* /usr/lib64/nagios/libexec

chmod 755 di /usr/lib64/nagios/libexec/* /etc/nagios/* /etc/nrpe.d/*
chown nagios:nagios di /usr/lib64/nagios/libexec/* /etc/nagios/* /etc/nrpe.d/*

service nrpe start


rm -rf /usr/local/nagios/bin/
rm -rf /usr/local/nagios/etc/*
rm -rf /usr/local/nagios/libexec/*

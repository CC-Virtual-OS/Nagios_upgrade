# Monitoring (nagios)

## This project performs the unistall and reinstall the nagios agent by performing the following operations:

 - Writes to a local file the hostname on which it is executed 
 - Create the nagios user with uid and password
 - Create the nagios group with gid 
 - Copy custom configuration files
 - Cleaning OS from nagios/nrpe packages
 - Installation of nagios-common and nrpe packages
 - Install nagios test plugins
 - Check nagios version
 - Risolto problema relativo allo user owner del servizio nrpe
 
 - Remediation of file nagios user permissions in case of uid change


Playbook use *nagios* role, it's tested on RHEL6 "santiago" and RHEL7 "maipo".

## Requirements

Require root permission to be executed.

## Variables

The variables are listed below :

| Name           | Example Value | Description                       |
| -------------- | ------------- | ----------------------------------|
| `nagios_pwd` | ***** | password for nagios user |
| `dest_app_dir` | "/tmp" | temp direcotry |
| `sybase_plugins_dir` | "/usr/lib64/nagios/sybase_plugins" | |
| `base_plugins_dir` | "/usr/lib64/nagios/base_plugins" | |

<<<<<<< HEAD
=======


## Dependencies

## Authors

>>>>>>> 2dcde851c1c93b9e55327f5530845a8211949a8d
 - Marco Simonetti [e4452](mailto:guest.simonetti.m@igt.com)
 - Danilo Abbasciano [e2594](mailto:guest.abbasciano.d@igt.com)

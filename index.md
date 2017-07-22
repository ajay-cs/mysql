## Installation of Mysql server on Centos/RHEL 7 server

#### 1) Set the hostname for your server
     ]#hostnamectl set-hostname dev
     
#### 2) Download and add the  community repository
     ]#wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
     
#### 3) Install the rpm mysql-community-release-el7-5.noarch.rpm
     ]#rpm -ivh mysql-community-release-el7-5.noarch.rpm
    
#### 4) Cross check Mysql repo is added as show below:
     ]# yum repolist
    Loaded plugins: fastestmirror, langpacks
    Loading mirror speeds from cached h}ostfile
     * base: ftp.iitm.ac.in
     * epel: mirror.rise.ph
     * extras: ftp.iitm.ac.in
     * updates: ftp.iitm.ac.in
    repo id                                                  repo name                                                              status
    base/7/x86_64                                            CentOS-7 - Base                                                         9,363
    epel/x86_64                                              Extra Packages for Enterprise Linux 7 - x86_64                         11,919
    extras/7/x86_64                                          CentOS-7 - Extras                                                         449
    mysql-connectors-community/x86_64                        MySQL Connectors Community                                                 36
    mysql-tools-community/x86_64                             MySQL Tools Community                                                      47
    mysql56-community/x86_64                                 MySQL 5.6 Community Server                                                344
    updates/7/x86_64                                         CentOS-7 - Updates                                                      2,130
    repolist: 24,288
    
#### 5) Yun yum update to update the all repo
     ]#yum update
      
#### 6) Install the mysql server
     ]#yum install mysql-server
     
#### 7) Start the msql server
     ]#systemctl start mysqld
 
#### 8) Allow to start the mysql server at boot time
     ]#systemctl enable mysqld
     
#### 9) Check the server started successfully.
     ]# systemctl status mysqld
      
      â mysqld.service - MySQL Community Server
         Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
         Active: active (running) since Sat 2017-07-22 12:05:47 IST; 14min ago
       Main PID: 27634 (mysqld_safe)
         CGroup: /system.slice/mysqld.service
                 ââ27634 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
                 ââ27800 /usr/sbin/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/l...

      Jul 22 12:05:44 dev mysql-systemd-start[27570]: 2017-07-22 12:05:44 27611 [Note] Binlog end
      Jul 22 12:05:44 dev mysql-systemd-start[27570]: 2017-07-22 12:05:44 27611 [Note] InnoDB: FTS optimize thread exiting.
      Jul 22 12:05:44 dev mysql-systemd-start[27570]: 2017-07-22 12:05:44 27611 [Note] InnoDB: Starting shutdown...
      Jul 22 12:05:46 dev mysql-systemd-start[27570]: 2017-07-22 12:05:46 27611 [Note] InnoDB: Shutdown completed; log sequence num...625987
      Jul 22 12:05:46 dev mysql-systemd-start[27570]: PLEASE REMEMBER TO SET A PASSWORD FOR THE MySQL root USER !
      Jul 22 12:05:46 dev mysql-systemd-start[27570]: To do so, start the server, then issue the following commands:
      Jul 22 12:05:46 dev mysql-systemd-start[27570]: /usr/bin/mysqladmin -u root password 'new-password'
      Jul 22 12:05:46 dev mysqld_safe[27634]: 170722 12:05:46 mysqld_safe Logging to '/var/log/mysqld.log'.
      Jul 22 12:05:46 dev mysqld_safe[27634]: 170722 12:05:46 mysqld_safe Starting mysqld daemon with databases from /var/lib/mysql
      Jul 22 12:05:47 dev systemd[1]: Started MySQL Community Server.
      Hint: Some lines were ellipsized, use -l to show in full.
      
-----------------End----------------------------

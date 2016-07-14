---
title:   "Hadoop Install"
excerpt: "steps for installing hadoop on centos6.x"
layout:  archive
author_profile: true
categories: 
  - job
tags:
  - hadoop
modified: 2016-07-14T16:27:37-04:00
---

__## step1  - add user hadoop__    

```bash
[root@localhost ~]# useradd -m hadoop -s /bin/bash    
[root@localhost ~]# passwd hadoop   
[root@localhost ~]# vim /etc/sudoers        /   sudo adduser hadoop sudo         
                    visudo =>  hadoop  ALL=(ALL)       ALL 
```

__## step2  -  ssh key__     

```bash
[hadoop@slave2 ~]$ rpm -qa | grep ssh      check installed ssh ornot
openssh-clients-5.3p1-84.1.el6.x86_64
libssh2-1.4.2-1.el6.x86_64
openssh-5.3p1-84.1.el6.x86_64
openssh-server-5.3p1-84.1.el6.x86_64

[hadoop@slave2 ~]$ sudo yum install openssh-clients
[hadoop@slave2 ~]$ sudo yum install openssh-server
[hadoop@slave2 ~]$ ssh-keygen -t rsa -P "" && ssh-copy-id -i ~/.ssh/id_rsa.pub hadoop@xx.xx.xx.xx
                   cd ~/.ssh/                          # if the dir is not exist，do ssh localhost first
                   cat id_rsa.pub >> authorized_keys   # add auth
                   chmod 600 ./authorized_keys         # change auth => if the auth is wrong, still can't access even with a key     
                   => the difinition of "~"
                      home dir of the user = /home/user 
``` 

__## step3 - install java__    

two kind of java, Linux system default setting is OpenJDK, CentOS 6.4 only install java jre  :    
  1. JDK of Oracle    
  2. OpenJDK    

```bash
[hadoop@slave2 ~]$ sudo yum install java-1.8.0-openjdk.x86_64 java-1.8.0-openjdk-devel.x86_64
```

then set JAVA_HOME in ~/.bashrc (/etc/bashrc => all user use)

```bash
export JAVA_HOME=/usr/lib/jvm/java-1.7.0-openjdk

[hadoop@slave2 ~]$ echo $JAVA_HOME    #check   
                   java -version    /    $JAVA_HOME/bin/java -version
```

__## step4 - install hadoop__    

```bash
install Hadoop at /usr/local (finish installation when uncompress the tar of hadoop)
download hadoop  =>  wget  http://apache.stu.edu.tw/hadoop/common/hadoop-2.6.4/hadoop-2.6.4.tar.gz
                     mv ./hadoop-2.6.0/ ./hadoop
                     ln -s /hadoop  /hadoop-2.6.0
unzip            =>  tar -zxf hadoop-2.6.4.tar.gz   /usr/local
                     chown -R hadoop:hadoop /usr/local/hadoop 

check            =>  /usr/local/hadoop/bin/hadoop version
```

__## step5 - setting__   
1. local    
2. Single node cluster    
3. cluster    

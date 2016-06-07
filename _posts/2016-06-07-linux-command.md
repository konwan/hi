---
title:   "Linux Command"
excerpt: "memo for linux command"
layout:  archive
author_profile: true
categories: 
  - job
tags:
  - linux
  - command
modified: 2016-06-07T12:27:37-04:00
---
## cd / mv / cp (enter dir, move or change name, copy)

```bash
> cd dir
> cd ~ (home directory)
> cd - (last directory)
> mv fileold filenew
> cp one anotherone
```



## ls / ll  (list file and dir)
 
```bash
> ls /tmpdir
> ls -al /tmpdir   (list all file, conclude conceal file <head with '.'>)  

-rw-r--r--  1   cindy cindy  2159 2016-05-06 14:53 a.py
drwxr-xr-x  1   cindy cindy  2984 2016-04-27 12:22 dir
---------- ---  ----- -----  ---- ---------- ----- ----
(1)        (2)  (3)   (4)    (5)  (6)        (7)   (8)
```


1. auth   
    ```bash
    d       rwx    r-x     rw-   
    type    owner  group   others
    
    #meaning: owner can read, write and execute; who in tho same group can read and execute
    ``` 
2. links (how many links to same i-node)
3. owner
4. group
5. size (bytes)
6. create date
7. create time
8. file name 

## chown / chgrp / chmod (change owner, group, auth)
```-R: Recursive```

```bash
> chown -R newowner:newgroup  dir
> chgrp newgroup file
> chmod number file
        owner = rwx = 4+2+1 = 7
        group = r-x = 4+0+1 = 5
        others= --- = 0+0+0 = 0
        => chmod 750 file 
        => means owner can read, write and execute; 
           who in tho same group can read and execute and others can do nothing
> chmod string file
        `+`: add
        `-`: delete
        `=`: assign
        
        `u`: owner
        `g`: group
        `o`: o
        `a`: all

        => chmod g+x file
        => means who in the same group can write
        => ex: o-rx, u=x,g=r,o= 
```




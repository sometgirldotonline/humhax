---
title: umount-proc-info
layout: default
parent: System
---

The device appears to be designed to dump running processes to the disk during a shutdown sequence. This behavior is evident from the `.umount-proc-info` files present in two distinct [partitions](/system/fs.html).


## Partition 1 (hmx_int_stor)

The output shows `/mnt/hd1` as the active target partition. You can see the explicit commands responsible for appending this data via PID `21155`.

```text
/mnt/hd1
652 /home/dama/dama /mnt/hd1/repository/23.dat
  PID USER       VSZ STAT COMMAND
    1 root      1708 S    init
    2 root         0 SW   [kthreadd]
    3 root         0 SW   [ksoftirqd/0]
    4 root         0 SW   [kworker/0:0]
    6 root         0 SW   [migration/0]
    7 root         0 SW   [migration/1]
    8 root         0 SW   [kworker/1:0]
    9 root         0 SW   [ksoftirqd/1]
   10 root         0 SW   [kworker/0:1]
   11 root         0 SW<  [khelper]
   93 root         0 SW   [sync_supers]
   95 root         0 SW   [bdi-default]
   96 root         0 SW<  [kblockd]
  101 root         0 SW<  [ata_sff]
  194 root         0 SW   [kswapd0]
  195 root         0 SW   [fsnotify_mark]
  196 root         0 SW<  [aio]
  198 root         0 SW<  [xfs_mru_cache]
  199 root         0 SW<  [xfslogd]
  200 root         0 SW<  [xfsdatad]
  201 root         0 SW<  [xfsconvertd]
  202 root         0 SW<  [crypto]
  288 root         0 SW   [kworker/1:1]
  291 root         0 SW<  [kstriped]
  301 root         0 SW   [mtdblock1]
  306 root         0 SW   [mtdblock2]
  311 root         0 SW   [mtdblock3]
  316 root         0 SW   [mtdblock4]
  325 root      1700 S    /bin/sh /etc/init.d/rcS
  431 root         0 SW   [ubi_bgt0d]
  436 root         0 SW   [mtdblock5]
  463 root         0 SW   [ubi_bgt1d]
  468 root         0 SW   [mtdblock6]
  487 root         0 SW   [mtdblock7]
  504 root         0 SW   [mtdblock8]
  520 root         0 SW   [ubifs_bgt1_1]
  532 root         0 SW   [ubifs_bgt1_0]
  537 root         0 SW   [ubifs_bgt1_2]
  554 root      1704 S    /usr/sbin/inetd
  573 root      451m S    /home/hama
  576 root      905m S    dfbmaster
  577 root      9708 S    /home/hamalauncher
  652 root     31064 S    [dama]
  653 root     11520 S    [comma]
  654 root      432m S    [imma]
  655 root     18620 S    [umma]
  656 root     11512 S    [tima]
  663 root     13900 S    [thma]
  664 root     11836 S    [pama]
  665 root     15404 S    [sama]
  671 root     79136 S    [nima]
  677 root      485m S    [obama]
  861 root     19712 S    [ipepg]
  862 root     12436 S    [remoteapp]
  863 root      470m S    [prism]
  865 root      731m S    [corsair]
  940 root     22044 S    [nxmanager]
  999 nobody    2148 S    proftpd: (accepting connections)
 1096 root         0 SW   [scsi_eh_0]
 1108 root         0 SW   [scsi_eh_1]
 1115 root         0 SW   [scsi_eh_2]
 1127 root         0 SW   [kworker/u:2]
 1132 root         0 SW   [kworker/u:3]
 1221 root         0 SW   [khubd]
 1388 root         0 SW<  [usbhid_resumer]
 1669 root         0 SW<  [kdmflush]
 1671 root         0 SW<  [kcryptd_io]
 1672 root         0 SW<  [kcryptd]
 1691 root         0 SW   [jbd2/sda1-8]
 1692 root         0 SW<  [ext4-dio-unwrit]
 1706 root         0 SW   [jbd2/sda2-8]
 1707 root         0 SW<  [ext4-dio-unwrit]
 1726 root         0 SW   [jbd2/sda3-8]
 1727 root         0 SW<  [ext4-dio-unwrit]
 1734 root         0 SW   [jbd2/dm-0-8]
 1735 root         0 SW<  [ext4-dio-unwrit]
 1807 root         0 SW   [RtmpTimerTask]
 1808 root         0 SW   [RtmpMlmeTask]
 1809 root         0 SW   [RtmpCmdQTask]
 1810 root         0 SW   [RtmpWscTask]
 1823 root      3928 S    wpa_supplicant -Bdddt -Dwext -i wlan0 -c /tmp/wpa.wl
18681 root         0 SW   [flush-8:0]
18969 root      620m R    ./netflix --idfile=/var/lib/humaxtv_user/netflix/man
19116 root      1712 S    udhcpc -t 3 -T 10 -p /tmp/udhcpc.pid.wlan0 -i wlan0
20829 root         0 SW   [flush-31:5]
21155 root      1696 S    sh -c ps >> /mnt/hd1/.umount-proc-info 
21157 root      1696 S    sh -c killall proftpd
21158 root      1700 R    ps
21159 root      1696 R    killall proftpd
30764 root     28208 S    [homma]

```

## Partition 2 (hmx_int_stor1)

This second log targets `/mnt/hd2`.
nice politics reference lol
also what the fuck is an LS doing at the top huh
```text
/mnt/hd2
677 /home/obama/obama   /mnt/hd2/Recordings/Movie_ Loving Pablo_20190707_2157.ts
677 /home/obama/obama   /mnt/hd2/Recordings/Movie_ Loving Pablo_20190707_2157.nts
  PID USER       VSZ STAT COMMAND
    1 root      1708 S    init
    2 root         0 SW   [kthreadd]
    3 root         0 SW   [ksoftirqd/0]
    6 root         0 SW   [migration/0]
   11 root         0 SW<  [khelper]
   93 root         0 SW   [sync_supers]
   95 root         0 SW   [bdi-default]
   96 root         0 SW<  [kblockd]
  101 root         0 SW<  [ata_sff]
  194 root         0 SW   [kswapd0]
  195 root         0 SW   [fsnotify_mark]
  196 root         0 SW<  [aio]
  198 root         0 SW<  [xfs_mru_cache]
  199 root         0 SW<  [xfslogd]
  200 root         0 SW<  [xfsdatad]
  201 root         0 SW<  [xfsconvertd]
  202 root         0 SW<  [crypto]
  290 root         0 SW<  [kstriped]
  300 root         0 SW   [mtdblock1]
  305 root         0 SW   [mtdblock2]
  310 root         0 SW   [mtdblock3]
  315 root         0 SW   [mtdblock4]
  324 root      1700 S    /bin/sh /etc/init.d/rcS
  431 root         0 SW   [ubi_bgt0d]
  437 root         0 SW   [mtdblock5]
  463 root         0 SW   [ubi_bgt1d]
  474 root         0 SW   [mtdblock6]
  490 root         0 SW   [mtdblock7]
  504 root         0 SW   [mtdblock8]
  554 root      1704 S    /usr/sbin/inetd
  573 root      451m S    /home/hama
  576 root      905m S    dfbmaster
  577 root      9708 S    /home/hamalauncher
  652 root     25276 S    [dama]
  653 root     11516 S    [comma]
  654 root      422m S    [imma]
  655 root     18748 S    [umma]
  656 root     11512 S    [tima]
  663 root     14564 S    [thma]
  664 root     11836 S    [pama]
  670 root     13620 S    [sama]
  671 root     79164 S    [nima]
  677 root      488m S    [obama]
  861 root     21892 S    [ipepg]
  862 root     12436 S    [remoteapp]
  863 root      470m S    [prism]
  865 root      657m S    [corsair]
 1069 root         0 SW   [scsi_eh_0]
 1079 root         0 SW   [scsi_eh_1]
 1090 root         0 SW   [scsi_eh_2]
 1174 root         0 SW   [khubd]
 1340 root         0 SW<  [usbhid_resumer]
 2026 root         0 SW<  [sysfsd]
 5594 root         0 SW   [kworker/u:0]
 6582 root         0 SW   [migration/1]
 6583 root         0 SW   [kworker/1:2]
 6584 root         0 SW   [ksoftirqd/1]
 6585 root         0 SW   [kworker/u:3]
 6601 root         0 SW   [kworker/1:0]
 6833 root         0 SW   [jbd2/sda2-8]
 6834 root         0 SW<  [ext4-dio-unwrit]
 6990 root         0 SW   [RtmpTimerTask]
 6991 root         0 SW   [RtmpMlmeTask]
 6992 root         0 SW   [RtmpCmdQTask]
 6993 root         0 SW   [RtmpWscTask]
 7037 root      3924 S    wpa_supplicant -Bdddt -Dwext -i wlan0 -c /tmp/wpa.wl
 9572 root     34516 S    [homma]
11736 root         0 SW   [flush-8:0]
15873 root         0 SW   [kworker/0:0]
21934 root         0 SW   [flush-ubifs_1_1]
21935 root         0 SW   [flush-ubifs_1_0]
21980 root         0 SW   [flush-ubifs_1_2]
22090 root      1696 S    sh -c ps >> /mnt/hd2/.umount-proc-info 
22091 root      1700 R    ps
22401 root         0 SW   [kworker/0:1]
27851 root         0 SW   [ubifs_bgt1_1]
27857 root         0 SW   [ubifs_bgt1_0]
27862 root         0 SW   [ubifs_bgt1_2]
28186 root     22052 S    [nxmanager]
```
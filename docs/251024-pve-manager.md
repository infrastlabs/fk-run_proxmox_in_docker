

```bash
# web
# https://172.29.40.252:8006 #root/root
  can\t open '/etc/ssh/ssh_host_rsa_key.pub' - No such file or directory (500)
  # mkdir -p /etc/ssh; touch /etc/ssh/ssh_host_rsa_key.pub
  #之后:概要页正常(headInfo+chart图表)

# TODO
# 无iso,无net:VM可启(与t1版效果一样)
#  1.添加ISO
#  2.添加NET<bridge,bond,vlan>; +OVS
#  3.存储STOR: ceph/ceph-cli的使用
#  4.集群CLUST: 多ct组集群, vm迁移

```

- ct-info

```bash
# imgs
root @ deb11-11 in ~ |16:59:01  
$ docker images |grep docker-pve
  registry.cn-shenzhen.aliyuncs.com/infrastlabs/docker-pve   v2501-deb11-t2  b0693486baa5   38 minutes ago   1.7GB
  registry.cn-shenzhen.aliyuncs.com/infrastlabs/docker-pve   v2501-deb11-t1  136898fa24bb   6 hours ago   2.45GB
  registry.cn-shenzhen.aliyuncs.com/infrastlabs/docker-pve   v2501-deb11  8247573e20d0   10 hours ago  982MB #/var/cache/apt/archives/*.deb

# pkgsize
root @ deb11-pve in /etc/ssh |16:54:11  
$ pkgsize
  6.82 Mbs  dpkg|1.20.13
  7.49 Mbs  perl-base|5.32.1-4+deb11u4
  7.56 Mbs  libjs-sencha-touch|2.4.2-1
  7.71 Mbs  libpython3.9-stdlib|3.9.2-1+deb11u3
  8.49 Mbs  geany-common|1.37.1-2
  8.52 Mbs  binutils-x86-64-linux-gnu|2.35.2-2
  8.76 Mbs  udev|247.3-7+1-pmx11u1
  9.57 Mbs  libgtk-3-0|3.24.24-4+deb11u4
  10.08 Mbs librsvg2-2|2.50.3+dfsg-1+deb11u1
  12.53 Mbs libc6|2.31-13+deb11u12
  # 13.03 Mbs librados2|14.2.21-1+deb11u1
  # 12.61 Mbs proxmox-backup-client|2.4.7-1
  # 13.50 Mbs proxmox-backup-file-restore|2.4.7-1
  13.57 Mbs binutils-common|2.35.2-2
  15.64 Mbs locales|2.31-13+deb11u13
  15.65 Mbs systemd|247.3-7+1-pmx11u1
  16.34 Mbs glusterfs-common|9.2-1
  17.05 Mbs perl-modules-5.32|5.32.1-4+deb11u4
  17.07 Mbs coreutils|8.32-4+b1
  19.60 Mbs iso-codes|4.6.0-1
  21.96 Mbs libjs-extjs|7.0.0-1
  24.36 Mbs samba-libs|2:4.13.13+dfsg-1~deb11u6
  24.99 Mbs libgtk-3-common|3.24.24-4+deb11u4
  25.01 Mbs cpp-10|10.2.1-6
  25.75 Mbs adwaita-icon-theme|3.38.0-1
  27.22 Mbs libperl5.32|5.32.1-4+deb11u4
  # 27.69 Mbs pve-docs|7.4-2
  # 29.01 Mbs lxc-pve|5.0.2-2
  32.38 Mbs libicu67|67.1-7+deb11u1
  34.45 Mbs git|1:2.30.2-1+deb11u5
  # 59.93 Mbs ceph-common|14.2.21-1+deb11u1
  # 274.55 Mbs   pve-edk2-firmware|3.20230228-4~bpo11+3
  # 283.40 Mbs   pve-qemu-kvm|7.2.10-1
  1563.61 Mbs  TOTALES

# top
  PID USER   PR  NI VIRT RES SHR S  %CPU  %MEM  TIME+ COMMAND 
  800 www-data  20   0  359.0m 141.9m  12.2m S   0.0   0.4   0:02.46 pveproxy worker  
  801 www-data  20   0  358.9m 141.9m  12.4m S   1.0   0.4   0:01.99 pveproxy worker  
  802 www-data  20   0  357.5m 140.9m  12.4m S   0.0   0.4   0:01.73 pveproxy worker  
  664 root   20   0  353.0m 137.1m  13.3m S   0.0   0.4   0:01.18 pvedaemon worke  
  653 root   20   0  352.3m 130.9m   7.5m S   0.0   0.4   0:00.82 pvedaemon worke  
  674 root   20   0  352.5m 130.8m   7.5m S   0.0   0.4   0:01.34 pvedaemon worke  
  799 www-data  20   0  345.6m 126.5m   3.0m S   0.0   0.4   0:00.03 pveproxy   
  642 root   20   0  344.1m 125.1m   3.0m S   0.0   0.4   0:00.03 pvedaemon  
  868 root   20   0  327.3m 103.8m   3.1m S   0.0   0.3   0:00.13 pvescheduler  
  788 root   20   0  332.5m 102.6m   3.8m S   0.0   0.3   0:00.11 pve-ha-crm 
  808 root   20   0  331.9m 102.2m   4.0m S   0.0   0.3   0:00.24 pve-ha-lrm 
  558 root   20   0  272.8m  89.8m   4.2m S   1.0   0.3   0:01.90 pve-firewall  
  554 root   20   0  267.7m  87.6m   7.1m S   0.7   0.3   0:02.07 pvestatd   
  215 root   20   0  588.0m  57.0m  49.9m S   0.3   0.2   0:01.67 pmxcfs  
  807 www-data  20   0   74.4m  52.4m   3.8m S   0.0   0.2   0:00.07 spiceproxy work  
  806 www-data  20   0   74.2m  51.6m   3.3m S   0.0   0.2   0:00.02 spiceproxy 
    1916 root   20   0 2735.2m  44.7m  12.6m S  10.0   0.1   0:22.52 kvm  
    39 root   20   0   31.3m  11.4m  10.5m S   0.0   0.0   0:00.33 systemd-journal  
    1 root   20   0  160.0m  10.1m   7.8m S   0.0   0.0   0:01.11 systemd 
  777 postfix   20   0   39.1m   6.3m   5.7m S   0.0   0.0   0:00.00 pickup  
  778 postfix   20   0   39.2m   6.2m   5.5m S   0.0   0.0   0:00.00 qmgr 
  162 root   20   0  109.1m   5.6m   5.0m S   0.0   0.0   0:00.04 systemd-logind   
  159 root   20   0   10.8m   5.1m   4.1m S   0.0   0.0   0:00.00 smartd  
    50 root   20   0   18.4m   4.8m   3.9m S   0.0   0.0   0:00.07 systemd-udevd 
  776 root   20   0   39.1m   4.8m   4.2m S   0.0   0.0   0:00.00 master  
  142 root   20   0  147.5m   4.1m   2.0m S   0.0   0.0   0:00.00 lxcfs   
    96 _rpc   20   0 7.7m   4.0m   3.5m S   0.0   0.0   0:00.00 rpcbind 
  138 message+  20   0 7.7m   3.7m   3.4m S   0.0   0.0   0:00.03 dbus-daemon   
  812 root   20   0 3.8m   3.6m   0.0m S   0.0   0.0   0:00.13 bash 
  190 root   20   0  645.9m   3.6m   2.4m S   0.0   0.0   0:00.31 rrdcached  
    2122 root   20   0 6.9m   3.3m   2.8m R   0.0   0.0   0:00.01 top  
  418 root   20   0 5.5m   2.6m   2.4m S   0.0   0.0   0:00.00 cron 
    89 root   20   0   78.3m   2.2m   2.0m S   0.0   0.0   0:00.18 pvefw-logger  
  172 root   20   0 2.8m   1.7m   1.6m S   0.0   0.0   0:00.00 agetty  
  144 root   20   0  271.8m   1.4m   1.2m S   0.0   0.0   0:00.00 pve-lxc-syscall  
  140 root   20   0 8.1m   1.4m   1.1m S   0.0   0.0   0:00.00 lxc-monitord  
  167 root   20   0 2.2m   0.6m   0.5m S   0.0   0.0   0:00.04 watchdog-mux  
  158 root   20   0 4.2m   0.1m   0.0m S   0.0   0.0   0:00.00 qmeventd 

root @ deb11-pve in / |16:46:05  
# pids
$ ps -ef |wc
  39  363 3082
$ ps -ef
  UID PID PPID  C STIME TTY TIME CMD
  root  1 0  3 16:45 ?  00:00:00 /lib/systemd/systemd log-level=info unit=sysinit.target
  root 39 1  2 16:45 ?  00:00:00 /lib/systemd/systemd-journald
  root 50 1  1 16:45 ?  00:00:00 /lib/systemd/systemd-udevd
  root 89 1  0 16:45 ?  00:00:00 /usr/sbin/pvefw-logger
  _rpc 96 1  0 16:45 ?  00:00:00 /sbin/rpcbind -f -w
  message+  138 1  0 16:46 ?  00:00:00 /usr/bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
  root   140 1  0 16:46 ?  00:00:00 /usr/libexec/lxc/lxc-monitord --daemon
  root   142 1  0 16:46 ?  00:00:00 /usr/bin/lxcfs /var/lib/lxcfs
  root   144 1  0 16:46 ?  00:00:00 /usr/lib/x86_64-linux-gnu/pve-lxc-syscalld/pve-lxc-syscalld --system /run/pve/lxc-syscalld.sock
  root   158 1  0 16:46 ?  00:00:00 /usr/sbin/qmeventd /var/run/qmeventd.sock
  root   159 1  0 16:46 ?  00:00:00 /usr/sbin/smartd -n
  root   162 1  0 16:46 ?  00:00:00 /lib/systemd/systemd-logind
  root   167 1  0 16:46 ?  00:00:00 /usr/sbin/watchdog-mux
  root   172 1  0 16:46 tty1  00:00:00 /sbin/agetty -o -p -- \u --noclear tty1 linux
  root   190 1  0 16:46 ?  00:00:00 /usr/bin/rrdcached -B -b /var/lib/rrdcached/db/ -j /var/lib/rrdcached/journal/ -p /var/run/rrdcached.pid -l unix:/var/run/rrdcached.sock
  root   215 1  1 16:46 ?  00:00:00 /usr/bin/pmxcfs
  root   418 1  0 16:46 ?  00:00:00 /usr/sbin/cron -f
  root   554 1  0 16:46 ?  00:00:00 pvestatd
  root   558 1  0 16:46 ?  00:00:00 pve-firewall
  root   642 1  0 16:46 ?  00:00:00 pvedaemon
  root   653  642  0 16:46 ?  00:00:00 pvedaemon worker
  root   664  642  0 16:46 ?  00:00:00 pvedaemon worker
  root   674  642  0 16:46 ?  00:00:00 pvedaemon worker
  root   776 1  0 16:46 ?  00:00:00 /usr/lib/postfix/sbin/master -w
  postfix   777  776  0 16:46 ?  00:00:00 pickup -l -t unix -u -c
  postfix   778  776  0 16:46 ?  00:00:00 qmgr -l -t unix -u
  root   788 1  0 16:46 ?  00:00:00 pve-ha-crm
  www-data  799 1  0 16:46 ?  00:00:00 pveproxy
  www-data  800  799  2 16:46 ?  00:00:00 pveproxy worker
  www-data  801  799  2 16:46 ?  00:00:00 pveproxy worker
  www-data  802  799  2 16:46 ?  00:00:00 pveproxy worker
  www-data  806 1  0 16:46 ?  00:00:00 spiceproxy
  www-data  807  806  0 16:46 ?  00:00:00 spiceproxy worker
  root   808 1  0 16:46 ?  00:00:00 pve-ha-lrm
  root   812 0  2 16:46 pts/0 00:00:00 bash
  root   868 1  1 16:46 ?  00:00:00 pvescheduler
  root   872  812  0 16:46 pts/0 00:00:00 ps -ef
root @ deb11-pve in / |16:46:06  
$ pstree
systemd-+-agetty
  |-cron
  |-dbus-daemon
  |-lxc-monitord
  |-lxcfs---2*[{lxcfs}]
  |-master-+-pickup
  |  `-qmgr
  |-pmxcfs---6*[{pmxcfs}]
  |-pve-firewall
  |-pve-ha-crm
  |-pve-ha-lrm
  |-pve-lxc-syscall---4*[{pve-lxc-syscall}]
  |-pvedaemon---3*[pvedaemon worke]
  |-pvefw-logger---{pvefw-logger}
  |-pveproxy---3*[pveproxy worker]
  |-pvescheduler
  |-pvestatd
  |-qmeventd
  |-rpcbind
  |-rrdcached---6*[{rrdcached}]
  |-smartd
  |-spiceproxy---spiceproxy work
  |-systemd-journal
  |-systemd-logind
  |-systemd-udevd
  `-watchdog-mux

# ports
$ ss -ntlp
State   Recv-Q  Send-Q   Local Address:Port Peer Address:Port  Process   
LISTEN  0 4096  0.0.0.0:111 0.0.0.0:*   users:(("rpcbind",pid=96,fd=4),("systemd",pid=1,fd=35))  
LISTEN  0 4096   127.0.0.1:85  0.0.0.0:*   users:(("pvedaemon worke",pid=674,fd=6),("pvedaemon worke",pid=664,fd=6),("pvedaemon worke",pid=653,fd=6),("pvedaemon",pid=642,fd=6))  
LISTEN  0 100   0.0.0.0:25  0.0.0.0:*   users:(("master",pid=776,fd=13)) 
LISTEN  0 4096  [::]:111 [::]:*   users:(("rpcbind",pid=96,fd=6),("systemd",pid=1,fd=37))  
LISTEN  0 4096  *:3128   *:*   users:(("spiceproxy work",pid=807,fd=6),("spiceproxy",pid=806,fd=6)) 
LISTEN  0 100   [::]:25  [::]:*   users:(("master",pid=776,fd=14)) 
LISTEN  0 4096  *:8006   *:*   users:(("pveproxy worker",pid=802,fd=6),("pveproxy worker",pid=801,fd=6),("pveproxy worker",pid=800,fd=6),("pveproxy",pid=799,fd=6))   
# sysd running
$ systemctl -a |grep runn
  init.scope   loaded active  running   System and Service Manager
  cron.service loaded active  running   Regular background program processing daemon
  dbus.service loaded active  running   D-Bus System Message Bus
  getty@tty1.service loaded active  running   Getty on tty1
  lxc-monitord.service  loaded active  running   LXC Container Monitoring Daemon
  lxcfs.service   loaded active  running   FUSE filesystem for LXC
  postfix@-.service  loaded active  running   Postfix Mail Transport Agent (instance -)
  pve-cluster.service   loaded active  running   The Proxmox VE cluster filesystem
  pve-firewall.service  loaded active  running   Proxmox VE firewall
  pve-ha-crm.service loaded active  running   PVE Cluster HA Resource Manager Daemon
  pve-ha-lrm.service loaded active  running   PVE Local HA Resource Manager Daemon
  pve-lxc-syscalld.service loaded active  running   Proxmox VE LXC Syscall Daemon
  pvedaemon.service  loaded active  running   PVE API Daemon
  pvefw-logger.service  loaded active  running   Proxmox VE firewall logger
  pveproxy.service   loaded active  running   PVE API Proxy Server
  pvescheduler.service  loaded active  running   Proxmox VE scheduler
  pvestatd.service   loaded active  running   PVE Status Daemon
  qmeventd.service   loaded active  running   PVE Qemu Event Daemon
  rpcbind.service loaded active  running   RPC bind portmap service
  rrdcached.service  loaded active  running   LSB: start or stop rrdcached
  smartmontools.service loaded active  running   Self Monitoring and Reporting Technology (SMART) Daemon
  spiceproxy.service loaded active  running   PVE SPICE Proxy Server
  systemd-journald.service loaded active  running   Journal Service
  systemd-logind.service   loaded active  running   User Login Management
  systemd-udevd.service loaded active  running   Rule-based Manager for Device Events and Files
  watchdog-mux.service  loaded active  running   Proxmox VE watchdog multiplexer
  dbus.socket  loaded active  running   D-Bus System Message Bus Socket
  rpcbind.socket  loaded active  running   RPCbind Server Activation Socket
  systemd-journald-audit.socket  loaded active  running   Journal Audit Socket
  systemd-journald-dev-log.socket   loaded active  running   Journal Socket (/dev/log)
  systemd-journald.socket  loaded active  running   Journal Socket
  systemd-udevd-control.socket   loaded active  running   udev Control Socket
  systemd-udevd-kernel.socket loaded active  running   udev Kernel Socket
```


```bash
# web
# https://172.29.40.252:8006 #root/root
  can't open '/etc/ssh/ssh_host_rsa_key.pub' - No such file or directory (500)


```

- ct-info

```bash
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


```bash
# pve-manager
root @ d586f2832885 in .../pve-manager/DEBIAN |22:57:50  
# $ ls |while read one; do echo ===$one; cat $one |grep aplinfo; done
  ===conffiles
  ===control
  ===md5sums
  f0a9ddc0fc02dbf35fd4dc08a5c05b3f  usr/share/doc/pve-manager/aplinfo.dat
  ===postinst
  cp /usr/share/doc/pve-manager/aplinfo.dat /var/lib/pve-manager/apl-info/download.proxmox.com

# mkdir $dst; 再装OK
root @ d586f2832885 in /tmp |23:02:04  
  $ mkdir -p /var/lib/pve-manager/apl-info/download.proxmox.com
  $ dpkg -i pve-manager_7.4-20_amd64.deb
```

- apt-offline

```bash
apt install -d/--download-only #/var/cache/apt/archives/目录下
apt download lftp #当前dir


root @ d9ec884cc2fb in .../apt/archives |06:46:02  
$ ls -lhSr |wc
  308  2765 23350
$ ls -lhSr 
  -rw-r--r-- 1 root root 1.5M May 13  2022 libproxmox-backup-qemu0_1.3.1-1_amd64.deb
  -rw-r--r-- 1 root root 1.5M Apr 23  2024 postfix_3.5.25-0+deb11u1_amd64.deb
  -rw-r--r-- 1 root root 1.6M May 29  2023 libjs-sencha-touch_2.4.2-1_all.deb
  -rw-r--r-- 1 root root 1.7M Mar 20  2025 libpython3.9_3.9.2-1+deb11u3_amd64.deb
  -rw-r--r-- 1 root root 1.8M Feb 21  2021 binutils-x86-64-linux-gnu_2.35.2-2_amd64.deb
  -rw-r--r-- 1 root root 1.9M Jun  9  2023 libpve-rs-perl_0.7.7_amd64.deb
  -rw-r--r-- 1 root root 2.1M Dec 22  2024 libgstreamer-plugins-base1.0-0_1.18.4-2+deb11u3_amd64.deb
  -rw-r--r-- 1 root root 2.2M Feb 21  2021 binutils-common_2.35.2-2_amd64.deb
  -rw-r--r-- 1 root root 2.2M Dec 16  2024 libgstreamer1.0-0_1.18.4-2.1+deb11u1_amd64.deb
  -rw-r--r-- 1 root root 2.7M Jun  7  2024 proxmox-backup-client_2.4.7-1_amd64.deb
  -rw-r--r-- 1 root root 2.7M Jun  2  2021 libjs-extjs_7.0.0-1_all.deb
  -rw-r--r-- 1 root root 2.7M Mar  8  2021 iso-codes_4.6.0-1_all.deb
  -rw-r--r-- 1 root root 2.8M Jun  7  2024 proxmox-backup-file-restore_2.4.7-1_amd64.deb
  -rw-r--r-- 1 root root 2.9M May 18  2021 libglusterd0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M May 18  2021 libgfxdr0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M May 18  2021 glusterfs-client_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M May 18  2021 libgfchangelog0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M May 18  2021 libgfrpc0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M May 18  2021 libgfapi0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.0M Sep 26 05:09 librados2_14.2.21-1+deb11u1_amd64.deb
  -rw-r--r-- 1 root root 3.2M May 18  2021 libglusterfs0_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 3.4M Feb 27  2023 lxc-pve_5.0.2-2_amd64.deb
  -rw-r--r-- 1 root root 4.3M Mar 26  2023 systemd_247.3-7+1-pmx11u1_amd64.deb
  -rw-r--r-- 1 root root 5.5M May 18  2021 glusterfs-common_9.2-1_amd64.deb
  -rw-r--r-- 1 root root 5.6M Mar 23  2024 samba-libs_2%3a4.13.13+dfsg-1~deb11u6_amd64.deb
  -rw-r--r-- 1 root root 9.8M Feb 27  2024 pve-edk2-firmware_3.20230228-4~bpo11+3_all.deb
  # -rw-r--r-- 1 root root  13M Mar 22  2023 pve-docs_7.4-2_all.deb
  -rw-r--r-- 1 root root  15M Sep 26 05:09 ceph-common_14.2.21-1+deb11u1_amd64.deb
  -rw-r--r-- 1 root root  25M Apr 11  2024 pve-qemu-kvm_7.2.10-1_amd64.deb
  # -rw-r--r-- 1 root root  74M Jul 26  2024 pve-kernel-5.15.158-2-pve_5.15.158-2_amd64.deb
  # -rw-r--r-- 1 root root  88M Oct 12  2023 pve-firmware_3.6-6_all.deb
```

- pve-kernel

```bash
root @ d586f2832885 in /tmp |23:08:30  
$ pkgsize |wc
  645  1935 21938
$ pkgsize  |grep pve |wc
 39 117  1269
$ pkgsize 
  6.82 Mbs	dpkg|1.20.13
  7.49 Mbs	perl-base|5.32.1-4+deb11u4
  7.56 Mbs	libjs-sencha-touch|2.4.2-1
  7.71 Mbs	libpython3.9-stdlib|3.9.2-1+deb11u3
  8.49 Mbs	geany-common|1.37.1-2
  8.52 Mbs	binutils-x86-64-linux-gnu|2.35.2-2
  8.76 Mbs	udev|247.3-7+1-pmx11u1
  9.57 Mbs	libgtk-3-0|3.24.24-4+deb11u4
  10.08 Mbs	librsvg2-2|2.50.3+dfsg-1+deb11u1
  12.53 Mbs	libc6|2.31-13+deb11u12
  12.61 Mbs	proxmox-backup-client|2.4.7-1
  13.03 Mbs	librados2|14.2.21-1+deb11u1
  13.50 Mbs	proxmox-backup-file-restore|2.4.7-1
  13.57 Mbs	binutils-common|2.35.2-2
  15.64 Mbs	locales|2.31-13+deb11u13
  15.65 Mbs	systemd|247.3-7+1-pmx11u1
  16.34 Mbs	glusterfs-common|9.2-1
  17.05 Mbs	perl-modules-5.32|5.32.1-4+deb11u4
  17.07 Mbs	coreutils|8.32-4+b1
  19.60 Mbs	iso-codes|4.6.0-1
  21.96 Mbs	libjs-extjs|7.0.0-1
  24.36 Mbs	samba-libs|2:4.13.13+dfsg-1~deb11u6
  24.99 Mbs	libgtk-3-common|3.24.24-4+deb11u4
  25.01 Mbs	cpp-10|10.2.1-6
  25.75 Mbs	adwaita-icon-theme|3.38.0-1
  27.22 Mbs	libperl5.32|5.32.1-4+deb11u4
  27.69 Mbs	pve-docs|7.4-2
  29.01 Mbs	lxc-pve|5.0.2-2
  32.38 Mbs	libicu67|67.1-7+deb11u1
  34.45 Mbs	git|1:2.30.2-1+deb11u5
  # 59.93 Mbs	ceph-common|14.2.21-1+deb11u1
  # 251.82 Mbs	pve-firmware|3.6-6
  # 274.55 Mbs	pve-edk2-firmware|3.20230228-4~bpo11+3
  # 283.40 Mbs	pve-qemu-kvm|7.2.10-1
  # 381.76 Mbs	pve-kernel-5.15.158-2-pve|5.15.158-2
  2207.18 Mbs	TOTALES

root @ d586f2832885 in /tmp |23:06:57  
$ apt -y remove pve-kernel
  Package 'pve-kernel' is not installed, so not removed
# $ apt remove pve-kernel
  Examining /etc/kernel/postinst.d.#############################.............................................................................] 
  run-parts: executing /etc/kernel/postinst.d/apt-auto-removal 5.15.158-2-pve /boot/vmlinuz-5.15.158-2-pve
  run-parts: executing /etc/kernel/postinst.d/initramfs-tools 5.15.158-2-pve /boot/vmlinuz-5.15.158-2-pve
  update-initramfs: Generating /boot/initrd.img-5.15.158-2-pve
  Running hook script 'zz-proxmox-boot'..
  Re-executing '/etc/kernel/postinst.d/zz-proxmox-boot' in new private mount namespace..
  unshare: unshare failed: Operation not permitted
  run-parts: /etc/initramfs/post-update.d//proxmox-boot-sync exited with return code 1
  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
  Failed to process /etc/kernel/postinst.d at /var/lib/dpkg/info/pve-kernel-5.15.158-2-pve.postinst line 19.
  dpkg: error processing package pve-kernel-5.15.158-2-pve (--configure):
  installed pve-kernel-5.15.158-2-pve package post-installation script subprocess returned error exit status 2
  dpkg: dependency problems prevent configuration of pve-kernel-5.15:
  pve-kernel-5.15 depends on pve-kernel-5.15.158-2-pve; however:
  Package pve-kernel-5.15.158-2-pve is not configured yet.

  dpkg: error processing package pve-kernel-5.15 (--configure):
  dependency problems - leaving unconfigured
  Processing triggers for initramfs-tools (0.140) ...
  update-initramfs: Generating /boot/initrd.img-5.15.158-2-pve############...................................................................] 
  Running hook script 'zz-proxmox-boot'..
  Re-executing '/etc/kernel/postinst.d/zz-proxmox-boot' in new private mount namespace..
  unshare: unshare failed: Operation not permitted
  run-parts: /etc/initramfs/post-update.d//proxmox-boot-sync exited with return code 1
  dpkg: error processing package initramfs-tools (--configure):
  installed initramfs-tools package post-installation script subprocess returned error exit status 1
  Errors were encountered while processing:
  ifupdown2
  pve-kernel-5.15.158-2-pve
  pve-kernel-5.15
  initramfs-tools
  E: Sub-process /usr/bin/dpkg returned an error code (1)
```

## 附

- apt-ins

```bash
root @ d9ec884cc2fb in /tmp |06:48:35  
# $ cat apt_ins_proxmox-ve.log |grep -v "http://"
The following NEW packages will be installed:
  apparmor attr binutils binutils-common binutils-x86-64-linux-gnu
  bridge-utils busybox ceph-common ceph-fuse cifs-utils corosync cpio criu
  cron cstream dmeventd dosfstools dtach ebtables faketime file
  fonts-font-awesome fonts-glyphicons-halflings gdisk genisoimage
  glusterfs-client glusterfs-common gnutls-bin hdparm ifupdown2
  initramfs-tools initramfs-tools-core ipset iso-codes keyutils klibc-utils
  kmod libaio1 libanyevent-http-perl libanyevent-perl libappconfig-perl
  libapt-pkg-perl libarchive13 libasyncns0 libauthen-pam-perl libbabeltrace1
  libbinutils libboost-context1.74.0 libboost-coroutine1.74.0
  libboost-iostreams1.74.0 libboost-program-options1.74.0
  libboost-thread1.74.0 libbytes-random-secure-perl libcbor0 libcephfs2
  libcfg7 libclone-perl libcmap4 libcommon-sense-perl libconvert-asn1-perl
  libcorosync-common4 libcpg4 libcrypt-openssl-bignum-perl
  libcrypt-openssl-random-perl libcrypt-openssl-rsa-perl
  libcrypt-random-seed-perl libcrypt-ssleay-perl libctf-nobfd0 libctf0 libdbi1
  libdevel-cycle-perl libdevmapper-event1.02.1 libdigest-hmac-perl
  libdrm-common libdrm2 libdw1 libedit2 libencode-locale-perl libfaketime
  libfdt1 libfido2-1 libfile-chdir-perl libfile-listing-perl
  libfile-readbackwards-perl libfilesys-df-perl libfuse3-3 libgbm1 libgfapi0
  libgfchangelog0 libgfrpc0 libgfxdr0 libglusterd0 libglusterfs0
  libgnutls-dane0 libgnutlsxx28 libgoogle-perftools4
  libgstreamer-plugins-base1.0-0 libgstreamer1.0-0 libhtml-parser-perl
  libhtml-tagset-perl libhtml-tree-perl libhttp-cookies-perl
  libhttp-daemon-perl libhttp-date-perl libhttp-message-perl
  libhttp-negotiate-perl libibverbs1 libinih1 libio-html-perl
  libio-multiplex-perl libio-socket-ssl-perl libio-stringy-perl libipset13
  libiscsi7 libjansson4 libjs-bootstrap libjs-extjs libjs-jquery
  libjs-qrcodejs libjs-sencha-touch libjson-perl libjson-xs-perl libklibc
  libknet1 libldb2 libleveldb1d liblinux-inotify2-perl liblmdb0 liblvm2cmd2.03

  libnl-route-3-200 libnozzle1 libnspr4 libnss3 libnuma1 liboath0 libopts25
  liborc-0.4-0 libpci3 libposix-strptime-perl libprotobuf-c1 libprotobuf23
  libproxmox-acme-perl libproxmox-acme-plugins libproxmox-backup-qemu0
  libproxmox-rs-perl libpulse0 libpve-access-control libpve-apiclient-perl
  libpve-cluster-api-perl libpve-cluster-perl libpve-common-perl
  libpve-guest-common-perl libpve-http-server-perl libpve-rs-perl
  libpve-storage-perl libpve-u2f-server-perl libpython3.9 libqb100
  libqrencode4 libquorum5 librabbitmq4 librados2 librados2-perl
  libradosstriper1 librbd1 librdmacm1 librrd8 librrds-perl libslirp0
  libsmbclient libsnappy1v5 libspice-server1 libstatgrab10
  libstring-shellquote-perl libtalloc2 libtcmalloc-minimal4 libtdb1
  libtemplate-perl libterm-readline-gnu-perl libtevent0 libtimedate-perl
  libtpms0 libtry-tiny-perl libtypes-serialiser-perl libu2f-server0
  libunbound8 libunwind8 liburcu6 liburi-perl liburing1 libusb-1.0-0
  libusbredirparser1 libuuid-perl libvirglrenderer1 libvotequorum8
  libwayland-server0 libwbclient0 libwrap0 libwww-perl libwww-robotrules-perl
  libxml-libxml-perl libxml-namespacesupport-perl libxml-parser-perl
  libxml-sax-base-perl libxml-sax-perl libxml-twig-perl libxslt1.1 libyaml-0-2
  libyaml-libyaml-perl linux-base logrotate lvm2 lxc-pve lxcfs lzop nfs-common
  novnc-pve openssh-client openssh-server openssh-sftp-server pci.ids pciutils
  perl-openssl-defaults postfix proxmox-archive-keyring proxmox-backup-client
  proxmox-backup-file-restore proxmox-kernel-helper proxmox-mail-forward
  proxmox-mini-journalreader proxmox-ve proxmox-websocket-tunnel
  proxmox-widget-toolkit pve-cluster pve-container pve-docs pve-edk2-firmware
  pve-firewall pve-firmware pve-ha-manager pve-i18n pve-kernel-5.15
  pve-kernel-5.15.158-2-pve pve-lxc-syscalld pve-manager pve-qemu-kvm
  pve-xtermjs python3-ceph-argparse python3-cephfs python3-certifi
  python3-chardet python3-idna python3-jwt python3-ldb python3-pkg-resources
  python3-prettytable python3-protobuf python3-rados python3-rbd
  python3-requests python3-six python3-talloc python3-urllib3 qemu-server
  qrencode rpcbind rrdcached runit-helper samba-common samba-libs
  smartmontools smbclient socat spiceterm sqlite3 ssl-cert swtpm swtpm-libs
  swtpm-tools systemd thin-provisioning-tools udev uidmap vncterm xfsprogs
  xsltproc zstd
The following packages will be upgraded:
  libgnutls30 libsystemd0 libudev1
3 upgraded, 302 newly installed, 1 to remove and 16 not upgraded.
Need to get 352 MB of archives.
After this operation, 1768 MB of additional disk space will be used.
# ...
Fetched 352 MB in 2min 15s (2612 kB/s)
Download complete and in download only mode
```

- dpkg--ig-deps

```bash
# mv pve-kernel-5.15.158-2-pve_5.15.158-2_amd64.deb pve-firmware_3.6-6_all.deb pve-docs_7.4-2_all.deb  ../
# dpkg -i --ignore-depends=pve-kernel-5.15.158-2-pve,proxmox-kernel-helper,pve-firmware,pve-docs *.deb

root @ d9ec884cc2fb in .../apt/archives |06:54:25  
# $ dpkg -i --ignore-depends=pve-kernel-5.15.158-2-pve,pve-firmware,pve-docs *.deb
  Processing triggers for libc-bin (2.31-13+deb11u12) ...
  Processing triggers for fontconfig (2.13.1-4.2) ...
  Processing triggers for desktop-file-utils (0.26-1) ...
  Processing triggers for hicolor-icon-theme (0.17-2) ...
  Processing triggers for initramfs-tools (0.140) ...
  Errors were encountered while processing:
  systemd_247.3-7+1-pmx11u1_amd64.deb
  ifupdown2
  # libpve-access-control
  # libpve-cluster-api-perl
  # libpve-guest-common-perl
  # libpve-storage-perl
  # librados2-perl
  proxmox-kernel-helper
  proxmox-ve
  pve-manager
  pve-cluster
  pve-container
  pve-firewall
  pve-ha-manager
  qemu-server
  $ echo $?
  1

root @ d9ec884cc2fb in .../apt/archives |07:14:59  
# sysd
$ find / -type f |grep systemd |sort |wc
  155 155  6750
  /lib/systemd/system/proxmox-boot-cleanup.service
  /lib/systemd/system/pve-cluster.service
  /lib/systemd/system/pve-container-debug@.service
  /lib/systemd/system/pve-container@.service
  /lib/systemd/system/pve-daily-update.service
  /lib/systemd/system/pve-daily-update.timer
  /lib/systemd/system/pve-firewall.service
  /lib/systemd/system/pve-guests.service
  /lib/systemd/system/pve-ha-crm.service
  /lib/systemd/system/pve-ha-lrm.service
  /lib/systemd/system/pve-lxc-syscalld.service
  /lib/systemd/system/pve-storage.target
  /lib/systemd/system/pvebanner.service
  /lib/systemd/system/pvedaemon.service
  /lib/systemd/system/pvefw-logger.service
  /lib/systemd/system/pvenetcommit.service
  /lib/systemd/system/pveproxy.service
  /lib/systemd/system/pvescheduler.service
  /lib/systemd/system/pvestatd.service
  /lib/systemd/system/qmeventd.service

# pkgs
$ dpkg -l |grep pve |wc
 36 327  4553
$ dpkg -l |grep pve
  ii  corosync 3.1.7-pve1 amd64  cluster engine daemon and utilities
  ii  criu 3.15-1+pve-1 amd64  checkpoint and restore in userspace
  ii  libcfg7:amd64  3.1.7-pve1 amd64  cluster engine CFG library
  ii  libcmap4:amd64 3.1.7-pve1 amd64  cluster engine CMAP library
  ii  libcorosync-common4:amd64  3.1.7-pve1 amd64  cluster engine common library
  ii  libcpg4:amd64  3.1.7-pve1 amd64  cluster engine CPG library
  ii  libjs-qrcodejs 1.20201119-pve1  all  javascript library for making cross-browser QRCodes
  ii  libknet1:amd64 1.24-pve2  amd64  kronosnet core switching implementation
  ii  libnozzle1:amd64 1.24-pve2  amd64  userland wrapper around kernel tap devices
  iU  libpve-access-control  7.4.3  all  Proxmox VE access control library
  ii  libpve-apiclient-perl  3.2-2  all  Proxmox VE API client library
  iU  libpve-cluster-api-perl  7.3-3  all  Proxmox Virtual Environment cluster Perl API modules.
  ii  libpve-cluster-perl  7.3-3  all  Proxmox Virtual Environment cluster Perl modules.
  ii  libpve-common-perl 7.4-2  all  Proxmox VE base library
  iU  libpve-guest-common-perl 4.2-5  all  Proxmox VE common guest-related modules
  ii  libpve-http-server-perl  4.3.0  all  Proxmox Asynchrounous HTTP Server Implementation
  ii  libpve-rs-perl 0.7.7  amd64  PVE parts which have been ported to Rust - Rust source code
  iU  libpve-storage-perl  7.4-4  all  Proxmox VE storage management library
  ii  libpve-u2f-server-perl 1.1-2  amd64  Perl bindings for libu2f-server
  ii  libquorum5:amd64 3.1.7-pve1 amd64  cluster engine Quorum library
  ii  libvotequorum8:amd64 3.1.7-pve1 amd64  cluster engine Votequorum library
  ii  lxc-pve  5.0.2-2  amd64  Linux containers userspace tools
  ii  lxcfs  5.0.3-pve1 amd64  LXC userspace filesystem
  ii  novnc-pve  1.4.0-1  all  HTML5 VNC client
  iU  pve-cluster  7.3-3  amd64  "pmxcfs" distributed cluster filesystem for Proxmox Virtual Environment.
  iU  pve-container  4.4-7  all  Proxmox VE Container management tool
  ii  pve-edk2-firmware  3.20230228-4~bpo11+3 all  edk2 based UEFI firmware modules for virtual machines
  iU  pve-firewall 4.3-5  amd64  Proxmox VE Firewall
  iU  pve-ha-manager 3.6.1  amd64  Proxmox VE HA Manager
  ii  pve-i18n 2.12-1 all  Internationalization support for Proxmox VE
  ii  pve-kernel-5.15  7.4-15 all  Latest Proxmox VE Kernel Image
  ii  pve-lxc-syscalld 1.2.2-1  amd64  PVE LXC syscall daemon
  iU  pve-manager  7.4-20 amd64  Proxmox Virtual Environment Management Tools
  ii  pve-qemu-kvm 7.2.10-1 amd64  Full virtualization on x86 hardware
  ii  pve-xtermjs  4.16.0-2 amd64  HTML/JS Shell client for Proxmox projects
  ii  smartmontools  7.2-pve3 amd64  control and monitor storage systems using S.M.A.R.T.
```


- docker-pve:v2501-deb11-t1 test run

```bash
# docker run -idt --network host --privileged --name pve --add-host pve:10.13.14.101 --hostname pve registry.cn-shenzhen.aliyuncs.com/infrastlabs/docker-pve:v2501-deb11-t1

root @ deb11-11 in .../apps/fk-run_proxmox_in_docker |11:14:56  |sam-custom ✓| 
$ docker exec -it pve bash
root @ pve in / |11:15:49  
$ ps -ef
UID  PID  PPID  C STIME TTY  TIME CMD
root 1 0  0 11:11 ?  00:00:00 /lib/systemd/systemd log-level=info unit=sysinit.target
root  38 1  0 11:11 ?  00:00:00 /lib/systemd/systemd-journald
root  49 1  0 11:11 ?  00:00:00 /lib/systemd/systemd-udevd
root 104 1  0 11:11 ?  00:00:00 /usr/sbin/pvefw-logger
_rpc 112 1  0 11:11 ?  00:00:00 /sbin/rpcbind -f -w
message+ 149 1  0 11:11 ?  00:00:00 /usr/bin/dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation 
root 151 1  0 11:11 ?  00:00:00 /usr/libexec/lxc/lxc-monitord --daemon
root 153 1  0 11:11 ?  00:00:00 /usr/bin/lxcfs /var/lib/lxcfs
root 158 1  0 11:11 ?  00:00:00 /usr/lib/x86_64-linux-gnu/pve-lxc-syscalld/pve-lxc-syscalld --system /run/pve/lxc-syscalld.
root 169 1  0 11:11 ?  00:00:00 /usr/sbin/qmeventd /var/run/qmeventd.sock
root 170 1  0 11:11 ?  00:00:00 /usr/sbin/smartd -n
root 176 1  0 11:11 ?  00:00:00 /lib/systemd/systemd-logind
root 178 1  0 11:11 ?  00:00:00 /usr/sbin/watchdog-mux
root 196 1  0 11:11 tty1 00:00:00 /sbin/agetty -o -p -- \u --noclear tty1 linux
root 217 1  0 11:11 ?  00:00:00 /usr/bin/rrdcached -B -b /var/lib/rrdcached/db/ -j /var/lib/rrdcached/journal/ -p /var/run/
root 234 1  0 11:11 ?  00:00:00 /usr/bin/pmxcfs
root 450 1  0 11:11 ?  00:00:00 /usr/sbin/cron -f
root 580 1  0 11:11 ?  00:00:00 pve-firewall
root 581 1  0 11:11 ?  00:00:00 pvestatd
root 759 1  0 11:11 ?  00:00:00 pvedaemon
root 767 759  0 11:11 ?  00:00:00 pvedaemon worker
root 771 759  0 11:11 ?  00:00:00 pvedaemon worker
root 776 759  0 11:11 ?  00:00:00 pvedaemon worker
root 790 1  0 11:11 ?  00:00:00 /usr/lib/postfix/sbin/master -w
postfix  791 790  0 11:11 ?  00:00:00 pickup -l -t unix -u -c
postfix  792 790  0 11:11 ?  00:00:00 qmgr -l -t unix -u
root 801 1  0 11:11 ?  00:00:00 pve-ha-crm
www-data 812 1  0 11:11 ?  00:00:00 pveproxy
www-data 813 812  0 11:11 ?  00:00:00 pveproxy worker
www-data 814 812  0 11:11 ?  00:00:00 pveproxy worker
www-data 815 812  0 11:11 ?  00:00:00 pveproxy worker
www-data 818 1  0 11:11 ?  00:00:00 spiceproxy
www-data 819 818  0 11:11 ?  00:00:00 spiceproxy worker
root 820 1  0 11:11 ?  00:00:00 pve-ha-lrm
root 825 1  0 11:11 ?  00:00:00 pvescheduler
root  1061 0  3 11:15 pts/1  00:00:00 bash
root  1116  1061  0 11:15 pts/1  00:00:00 ps -ef
root @ pve in / |11:15:51  
$ pstree
systemd-+-agetty
  |-cron
  |-dbus-daemon
  |-lxc-monitord
  |-lxcfs---2*[{lxcfs}]
  |-master-+-pickup
  |  `-qmgr
  |-pmxcfs---5*[{pmxcfs}]
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
  |-rrdcached---9*[{rrdcached}]
  |-smartd
  |-spiceproxy---spiceproxy work
  |-systemd-journal
  |-systemd-logind
  |-systemd-udevd
  `-watchdog-mux

root @ deb11-pve in / |11:23:28  
$ ss -ntlp
State  Recv-Q Send-Q Local Address:Port  Peer Address:Port Process  
LISTEN 0  4096 0.0.0.0:111  0.0.0.0:* users:(("rpcbind",pid=89,fd=4),("systemd",pid=1,fd=35)) 
LISTEN 0  4096 127.0.0.1:85 0.0.0.0:* users:(("pvedaemon worke",pid=707,fd=6),("pvedaemon worke",pid=703,fd=6),("pvedaemon worke",pid=697,fd=6),("pvedaemon",pid=690,fd=6)) 
LISTEN 0  128  0.0.0.0:22 0.0.0.0:* users:(("sshd",pid=165,fd=3)) 
LISTEN 0  100  0.0.0.0:25 0.0.0.0:* users:(("master",pid=773,fd=13))  
LISTEN 0  4096  [::]:111 [::]:* users:(("rpcbind",pid=89,fd=6),("systemd",pid=1,fd=37)) 
LISTEN 0  128 [::]:22  [::]:* users:(("sshd",pid=165,fd=4)) 
LISTEN 0  4096 *:3128 *:* users:(("spiceproxy work",pid=803,fd=6),("spiceproxy",pid=802,fd=6))  
LISTEN 0  100 [::]:25  [::]:* users:(("master",pid=773,fd=14))  
LISTEN 0  4096 *:8006 *:* users:(("pveproxy worker",pid=799,fd=6),("pveproxy worker",pid=798,fd=6),("pveproxy worker",pid=797,fd=6),("pveproxy",pid=796,fd=6))  

# sysd running
$ systemctl -a |grep runn
  init.scope   loaded    active running   System and Service Manager
  cron.service loaded    active running   Regular background program processing daemon
  dbus.service loaded    active running   D-Bus System Message Bus
  lxc-monitord.service loaded    active running   LXC Container Monitoring Daemon
  lxcfs.service    loaded    active running   FUSE filesystem for LXC
  postfix@-.service    loaded    active running   Postfix Mail Transport Agent (instance -)
  pve-cluster.service  loaded    active running   The Proxmox VE cluster filesystem
  pve-firewall.service loaded    active running   Proxmox VE firewall
  pve-ha-crm.service   loaded    active running   PVE Cluster HA Resource Manager Daemon
  pve-ha-lrm.service   loaded    active running   PVE Local HA Resource Manager Daemon
  pve-lxc-syscalld.service loaded    active running   Proxmox VE LXC Syscall Daemon
  pvedaemon.service    loaded    active running   PVE API Daemon
  pvefw-logger.service loaded    active running   Proxmox VE firewall logger
  pveproxy.service loaded    active running   PVE API Proxy Server
  pvescheduler.service loaded    active running   Proxmox VE scheduler
  pvestatd.service loaded    active running   PVE Status Daemon
  qmeventd.service loaded    active running   PVE Qemu Event Daemon
  rpcbind.service  loaded    active running   RPC bind portmap service
  rrdcached.service    loaded    active running   LSB: start or stop rrdcached
  smartmontools.service    loaded    active running   Self Monitoring and Reporting Technology (SMART) Daemon
  spiceproxy.service   loaded    active running   PVE SPICE Proxy Server
  ssh.service  loaded    active running   OpenBSD Secure Shell server
  systemd-journald.service loaded    active running   Journal Service
  systemd-logind.service   loaded    active running   User Login Management
  systemd-udevd.service    loaded    active running   Rule-based Manager for Device Events and Files
  watchdog-mux.service loaded    active running   Proxmox VE watchdog multiplexer
  dbus.socket  loaded    active running   D-Bus System Message Bus Socket
  rpcbind.socket   loaded    active running   RPCbind Server Activation Socket
  systemd-journald-audit.socket    loaded    active running   Journal Audit Socket
  systemd-journald-dev-log.socket  loaded    active running   Journal Socket (/dev/log)
  systemd-journald.socket  loaded    active running   Journal Socket
  systemd-udevd-control.socket loaded    active running   udev Control Socket
  systemd-udevd-kernel.socket  loaded    active running   udev Kernel Socket
```

- apt-sub size

```bash
root @ 38927ff7b96c in / |15:02:18  
# [181> 352 MB]
$ apt install --no-install-recommends proxmox-ve
  3 upgraded, 302 newly installed, 1 to remove and 16 not upgraded.
  Need to get 352 MB of archives.
  After this operation, 1768 MB of additional disk space will be used.

# [pve-qemu-kvm>> ifenslave>> pve-manager]再装: 
#  {initramfs-tools linux-base openssh-server}
#  {proxmox-archive-keyring proxmox-kernel-helper pve-firmware pve-kernel-5.15 pve-kernel-5.15.158-2-pve}
$ apt install --no-install-recommends proxmox-ve
  The following NEW packages will be installed:
    busybox dosfstools initramfs-tools initramfs-tools-core klibc-utils kmod libcbor0 libfido2-1 libklibc linux-base openssh-client openssh-server openssh-sftp-server proxmox-archive-keyring proxmox-kernel-helper proxmox-ve
    pve-firmware pve-kernel-5.15 pve-kernel-5.15.158-2-pve runit-helper
  0 upgraded, 20 newly installed, 0 to remove and 16 not upgraded.
  Need to get 171 MB of archives.
  After this operation, 673 MB of additional disk space will be used.


# [pve-qemu-kvm]>> Need to get 93.5 MB of archives.
# 无:pve-kernel/firmware
#  {glusterfs-client nfs-common samba-common novnc-pve qemu-server}
#  {proxmox-backup-client proxmox-backup-file-restore proxmox-mail-forward proxmox-mini-journalreader proxmox-websocket-tunnel proxmox-widget-toolkit pve-cluster pve-container pve-docs pve-edk2-firmware pve-firewall pve-ha-manager pve-i18n pve-lxc-syscalld pve-manager pve-xtermjs}
$ apt install --no-install-recommends pve-manager
  3 upgraded, 282 newly installed, 1 to remove and 16 not upgraded.
  Need to get 181 MB of archives.
  After this operation, 1094 MB of additional disk space will be used.

####################
# kernel [79.7> 171 MB]
$ apt install --no-install-recommends pve-kernel-5.15
  The following NEW packages will be installed:  ##+{pve-firmware pve-kernel-5.15} [79.7> 171 MB]
    busybox cpio initramfs-tools initramfs-tools-core klibc-utils kmod libklibc linux-base pve-firmware pve-kernel-5.15 pve-kernel-5.15.158-2-pve udev
  1 upgraded, 12 newly installed, 0 to remove and 18 not upgraded.
  Need to get 171 MB of archives.
  After this operation, 677 MB of additional disk space will be used.

$ apt install --no-install-recommends pve-kernel-5.15.158-2-pve
  The following NEW packages will be installed:
    busybox cpio initramfs-tools initramfs-tools-core klibc-utils kmod libklibc linux-base pve-kernel-5.15.158-2-pve udev
  1 upgraded, 10 newly installed, 0 to remove and 18 not upgraded.
  Need to get 79.7 MB of archives.
  After this operation, 413 MB of additional disk space will be used.

# firmware
$ apt install --no-install-recommends pve-firmware #x1
  0 upgraded, 1 newly installed, 0 to remove and 19 not upgraded.
  Need to get 91.3 MB of archives.
  After this operation, 264 MB of additional disk space will be used.

$ apt install --no-install-recommends pve-edk2-firmware #x1
  0 upgraded, 1 newly installed, 0 to remove and 19 not upgraded.
  Need to get 10.2 MB of archives.
  After this operation, 288 MB of additional disk space will be used.

####################
# qemu {ceph-common glusterfs-common} 87.7 MB
$ apt install --no-install-recommends pve-qemu-kvm
  0 upgraded, 72 newly installed, 0 to remove and 19 not upgraded.
  Need to get 87.7 MB of archives.
  After this operation, 491 MB of additional disk space will be used.

# ceph-common
$ apt install --no-install-recommends ceph-common
  0 upgraded, 37 newly installed, 0 to remove and 19 not upgraded.
  Need to get 26.5 MB of archives.
  After this operation, 111 MB of additional disk space will be used.

$ apt install --no-install-recommends glusterfs-common
  0 upgraded, 22 newly installed, 0 to remove and 19 not upgraded.
  Need to get 26.2 MB of archives.
  After this operation, 44.6 MB of additional disk space will be used.

# backup
$ apt install --no-install-recommends proxmox-backup-client
  0 upgraded, 4 newly installed, 0 to remove and 19 not upgraded.
  Need to get 2947 kB of archives.
  After this operation, 13.7 MB of additional disk space will be used.

$ apt install --no-install-recommends proxmox-backup-file-restore
  0 upgraded, 1 newly installed, 0 to remove and 19 not upgraded.
  Need to get 2832 kB of archives.
  After this operation, 14.2 MB of additional disk space will be used.

# sysd
$ apt install --no-install-recommends systemd
  1 upgraded, 1 newly installed, 1 to remove and 18 not upgraded.
  Need to get 4877 kB of archives.
  After this operation, 16.1 MB of additional disk space will be used.


```

- pve-manager deps:{ifenslave ifupdown2}

```bash
$ apt install --no-install-recommends pve-manager
  Setting up ifupdown2 (3.1.0-1+pmx4) ...############.......] 
  find: '/var/lib/dhcp/': No such file or directory
  Creating /etc/network/interfaces.
  network config changes have been detected for ifupdown2 compatibility.
  Saved in /etc/network/interfaces.new for hot-apply or next reboot.
  Reloading network config on first install
  ##error: Another instance of this program is already running.
  dpkg: error processing package ifupdown2 (--configure):
  installed ifupdown2 package post-installation script subprocess returned error exit status 89
  # ...
  # ifupdown2 ifenslave
  dpkg: dependency problems prevent configuration of pve-manager:
  pve-manager depends on ifupdown2 (>= 2.0.1-1+pve8) | ifenslave (>= 2.6); however:
    Package ifupdown2 is not configured yet.
    Package ifenslave is not installed.
  dpkg: error processing package pve-manager (--configure):
  dependency problems - leaving unconfigured  
  # ..
  Created symlink /etc/systemd/system/multi-user.target.wants/qmeventd.service -> /lib/systemd/system/qmeventd.service.
  Processing triggers for dbus (1.12.28-0+deb11u1) ...
  Processing triggers for fontconfig (2.13.1-4.2) ...
  Processing triggers for libc-bin (2.31-13+deb11u12) ...
  Processing triggers for pve-ha-manager (3.6.1) ...
  System has not been booted with systemd as init system (PID 1). Can't operate.
  Failed to connect to bus: Host is down
  System has not been booted with systemd as init system (PID 1). Can't operate.
  Failed to connect to bus: Host is down
  Errors were encountered while processing:
  ifupdown2
  pve-manager
  E: Sub-process /usr/bin/dpkg returned an error code (1)

# ref src\Dockerfile.x11deb-t2
  #ifupdown2[ERR; 237 kB] ifenslave [OK; 98.0 kB] ##ifenslave装后: pve-manager无ifupdown2依赖项了,安装ok
  RUN apt.sh ifenslave;
  # RUN apt.sh ifupdown2;

  # apt install --no-install-recommends 
  RUN apt.sh pve-qemu-kvm;
  RUN apt.sh pve-manager;
  # RUN apt.sh proxmox-ve;

```
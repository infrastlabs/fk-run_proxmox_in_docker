- vers
  - pve9.0--deb13
  - pve8.4--deb12
  - pve7.4--deb11

### 251023-proxmox-pve

- pve-manager [181 MB] #安装免错 `ifenslave/ifupdown1>> pve-manager`
- proxmox-pve [352 MB]
  - {initramfs-tools linux-base openssh-server}
  - {proxmox-archive-keyring proxmox-kernel-helper pve-firmware pve-kernel-5.15 pve-kernel-5.15.158-2-pve}


### 251024-pve-manager

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

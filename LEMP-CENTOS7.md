LEPM CENTOS 7
1. disable selinux dengan cara mengubah SELINUX=enforcing menjadi SELINUX=disabled
\
caranya
```plaintext 
sudo vi /etc/selinux/config
```
lalu tekan huruf **i** di keyboard yang berfungsi sebagai insert atau supaya bisa mengedit file tersebut
```plaintext
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected. 
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```
\
simpan hasil edit dengan cara tekan tombol **ESC** dan ketik **:wq!** kemudian lakukan reboot dengan perintah
```plaintext 
sudo reboot
```
lakukan installasi tools untuk mempermudah dalam proses selanjutnya
\
install ssh, wget, unzip, net-tools
```plaintext 
sudo yum install -y openssh-server wget unzip net-tools
```
install epel-release nginx
```plaintext
sudo yum -y install epel-release nginx
```
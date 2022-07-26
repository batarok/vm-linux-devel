# LEPM CENTOS 7
1. disable selinux dengan cara mengubah SELINUX=enforcing menjadi SELINUX=disabled
\
caranya
```plaintext 
sudo vi /etc/selinux/config
```
lalu tekan huruf **i** di keyboard yang berfungsi sebagai insert atau supaya bisa mengedit file tersebut
![disabled-selinux](/asset/image/disabled-selinux.png)
\
simpan hasil edit dengan cara tekan tombol **ESC** dan ketik **:wq!** kemudian lakukan reboot dengan perintah
```plaintext 
sudo reboot
```
1. Lakukan installasi tools untuk mempermudah dalam proses selanjutnya
\
install ssh, wget, unzip, net-tools
```plaintext 
sudo yum install -y openssh-server wget unzip net-tools curl
```
3. Install webserver nginx
install epel-release nginx
```plaintext
sudo yum -y install epel-release nginx
```
Aktifkan dan jalankan service nginx dengan perintah berikut
- gunakan perintah dibawah supaya service nginx bisa berjalan saat vm di reboot
```plaintext
sudo systemctl enable nginx
```
- jalankan service nginx
```plaintext
sudo systemctl start nginx
```
- lakukan pengecekan service nginx
```plaintext
sudo systemctl status nginx
```
Setelah itu coba akses website menggunakan url http://127.0.0.1:880 atau sesuai port yang sudah diseting di sesi ![**install centos 7 di virtualbox**](1_install_centos7_vbox_win10.md) \
Jika hasil akses url nya gagal berarti melakukan open port http, untuk caranya
```plaintext
firewall-cmd --zone=public --add-port=80/tcp --permanent
```
Lalu lakukan reload firewall-cmd
```plaintext
firewall-cmd --reload
```
Setelah hal ini dilakukan seharusnya website sudah dapat diakses. \
1. Install php-fpm
Untuk installasi php-fpm perlu melakukan hal ini \
```plaintext
sudo yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
```
```plaintext
sudo yum -y install yum-utils
```
Gunakan perintah dibawah ini untuk melakukan pengecekan versi php-fpm yang tersedia
```plaintext 
yum --disablerepo="*" --enablerepo="remi-safe" list php[7-9][0-9].x86_64
```
# Install Agro Tunnel Cloudflare di Centos 7
1. Daftar atau login cloudflare \
2. Download file cloudflared [disini](https://github.com/cloudflare/cloudflared/releases), untuk centos download file ekstensi .rpm
3. Install file .rmp dengan perintah \
```sudo rpm -i namafile.rpm```
Setelah berhasil terinstall jalankan perintah ```cloudflared tunnel login``` nantinya akan ada link yang ditampilak di layar ssh, copy link tersebut dan akses melalui browser yang sudah login ke akun cloudflare
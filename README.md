# My Infrastructure Script.
> ปกติแล้วตัวผมเองเป็นคนที่เขียนฝั่ง Application ซะส่วนใหญ่ บ่อยครั้งที่ต้องดิ้นรนมาสร้าง Cloud, เซ็ต Server, ติดตั้ง Nginx, Php, NodeJS, ทำ Reverse Proxy อะไรต่างๆ นานาอีกมากมาย ซึ่งหลายครั้ง ก็ทำได้ .. หลายครั้งก็ทำแล้วพัง
>
> จนวันนี้ตัดสินใจแล้วว่า ตั้งแต่นี้ทำไรไปจะจดละ ! จะได้ไม่ลืมเธอ 🌹

เก็บทุกอย่างที่เคยใช้ Setting Server เอาไว้ !

## Content
* Nginx with nginx.repo
* Nginx serv static file
* Nginx Reverse Proxy
* Nginx serv PHP via TCP/IP
* Nginx Vhost
* MariaDB with MariaDB.repo
* firewalld and firewall-cmd
* vsftpd - Secure, fast FTP server for UNIX-like systems
* Installing NodeJS with NVM
* PM2 : nodejs task running management
* How to kill port 3000
* Access Logs / Error Logs of Nginx
* User Management
  * Adduser
  * add Password to user
  * Group
* Permission
  * Onwer / Group / Other
* SSL with Certbot & Let's Encrypt

---

## Nginx with nginx.repo
> https://www.nginx.com/resources/wiki/start/topics/tutorials/install/

1. ขั้นแรกให้เพิ่ม NGINX yum repository ก่อน, โดยสร้างไฟล์ที่ `/etc/yum.repos.d/nginx.repo` โดยเอาสิ่งที่อยู่ด้านล่างไปแปะ

```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=0
enabled=1
```

2. สั่ง `yum install nginx` ซะ! แล้วเชคดูให้ดีว่า nginx ที่ติดตั้งนั้นเป็น version ล่าสุดหรือยัง ? ถ้าล่าสุดแล้ว คือว่าทำถูกต้อง
# Bài 4: Cấu hình tường lửa bảo vệ máy chủ (UFW & Cloud Firewall Integration)

## 1. Trạng thái UFW trên OS (Lớp 1)
Dưới đây là đầu ra của lệnh `sudo ufw status verbose` khi chạy trên Droplet:

<img width="929" height="835" alt="image" src="https://github.com/user-attachments/assets/b7401760-527e-4366-beea-ff939a65de90" />



C:\Users\Admin>ssh root@221.121.3.175
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-63-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Thu Oct  1 08:31:26 2026 from 113.171.152.53
root@hungpham:~# sudo ufw default deny incoming
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)
root@hungpham:~# sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
root@hungpham:~# sudo allow 22/tcp
sudo: allow: command not found
root@hungpham:~# sudo ufw allow 22/tcp
Rule added
Rule added (v6)
root@hungpham:~# sudo ufw allow 80/tcp
Rule added
Rule added (v6)
root@hungpham:~# sudo ufw enable
Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup
root@hungpham:~# sudo ufw status verbose
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
80,443/tcp (Nginx Full)    ALLOW IN    Anywhere
22/tcp (OpenSSH)           ALLOW IN    Anywhere
22/tcp                     ALLOW IN    Anywhere
80/tcp                     ALLOW IN    Anywhere
80,443/tcp (Nginx Full (v6)) ALLOW IN    Anywhere (v6)
22/tcp (OpenSSH (v6))      ALLOW IN    Anywhere (v6)
22/tcp (v6)                ALLOW IN    Anywhere (v6)
80/tcp (v6)                ALLOW IN    Anywhere (v6)

root@hungpham:~#

# Linux_h_w.06

Установить Nginx и настроить его на работу с PHP-FPM.
    
    apt install nginx
    cd /etc/nginx
    cd /etc/nginx
    nano nginx.conf
    nginx -t
    systemctl reload nginx
    nano default
   
Установить Apache. Настроить обработку PHP. Добиться одновременной работы с Nginx.
    apt install apache2
    systemctl start apache2
    /etc/apache2/ports.conf
    Listen 127.0.0.1:8080
    /etc/apache2# ss -ntpl
    State              Recv-Q              Send-Q                           Local Address:Port                           Peer Address:Port             Process
    LISTEN             0                   128                                    0.0.0.0:22                                  0.0.0.0:*                 users:(("sshd",pid=765,fd=3))
    LISTEN             0                   511                                    0.0.0.0:80                                  0.0.0.0:*                 users:(("nginx",pid=3119,fd=6),("nginx",pid=3118,fd=6),("nginx",pid=3117,fd=6),("nginx",pid=3116,fd=6),("nginx",pid=2953,fd=6))
    LISTEN             0                   4096                             127.0.0.53%lo:53                                  0.0.0.0:*                 users:(("systemd-resolve",pid=460,fd=14))
    LISTEN             0                   128                                  127.0.0.1:631                                 0.0.0.0:*                 users:(("cupsd",pid=743,fd=7))
    LISTEN             0                   128                                       [::]:22                                     [::]:*                 users:(("sshd",pid=765,fd=4))
    LISTEN             0                   511                                       [::]:80                                     [::]:*                 users:(("nginx",pid=3119,fd=7),("nginx",pid=3118,fd=7),("nginx",pid=3117,fd=7),("nginx",pid=3116,fd=7),("nginx",pid=2953,fd=7))
    LISTEN             0                   511                                          *:8080                                      *:*                 users:(("apache2",pid=3941,fd=4),("apache2",pid=3940,fd=4),("apache2",pid=3939,fd=4))
    LISTEN             0                   128                                      [::1]:631                                    [::]:*                 users:(("cupsd",pid=743,fd=6))
root@vladislav-linux:/etc/apache2# ll

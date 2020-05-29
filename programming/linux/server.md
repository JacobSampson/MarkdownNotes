# Server

## Setup

[Guide](https://www.tecmint.com/initial-ubuntu-server-setup-guide/)

### General

`sudo su -`: change to root  
`timedatectl set-timezone America/Chicago`: set the time zone to Central

## **Securing and Monitoring**

### SSH

`/etc/ssh/sshd_config`

* Port 
* PermitRootLogin no
* PubkeyAuthentication yes
* PasswordAuthentication no

`sudo systemctly restart sshd`

`ssh -p PORT USERNAME@IP -i PATH`

### Firewall

UFW: Uncomplicated Firewall

`ss`

* `-a`: all
* `-n`: numbers
* `-p`: process in charge of socket
* `-t`: TCP sockets
* `-u`: UDP

### Logs

`/var/log/sys_log`

## **Configuring and Managing**

`sudo vi /etc/netplan/...`

`top`: view processes and users

* `iotop`: input/output
* `iftop`

`renice`: specify priority

### Service Management

`systemctl`

* `-t`: target
* `start/stop`

### User Accounts

`adduser`  
`usermod`  
`deluser`

## **Services**

### HTTP Server and TLS

Apache 2: [digitalocean.com](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-18-04)  
Setup virtual hosts: \[digitalocean.com\]\([https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-18-04\#step-5-%E2%80%94-setting-up-virtual-hosts-\(recommended](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-18-04#step-5-%E2%80%94-setting-up-virtual-hosts-%28recommended)\)\)  
Secure Apache2: [digitalocean.com](https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-18-04)

Several name-based web sites: [apache.org](https://httpd.apache.org/docs/2.4/vhosts/examples.html)

Reroute to `www` _and_ `https`

```text
RewriteEngine on
RewriteCond %{HTTPS} off [OR]
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule (.*) https://www.example.com%{REQUEST_URI} [R=301,L]
```

`sudo chown -R www-data:www-data /var/www` ?  
Edit domain-le-ssl.conf if changing source folder, after creating SSL certificate


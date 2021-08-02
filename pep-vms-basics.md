# PEP VM Basic Commands
All of the following was tested to work on CentOS 7
## Install Base Packages
```bash
yum install epel-release
yum update
```
(nano is just personal preference, not required)
```bash
yum install nano
```

## Disable SELinux
```bash
sudo setenforce 0
```
edit file `/etc/selinux/config` and set `SELINUX=disabled`
```bash
sudo nano /etc/selinux/config
```

## Enable Firewalld
```bash
systemctl enable firewalld
systemctl start firewalld
```

## Create Swap Space
```bash
sudo dd if=/dev/zero of=/swapfile count=4096 bs=1MiB
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
```
edit file `/etc/fstab` add line `/swapfile   swap    swap    sw  0   0` at the end
```bash
sudo nano /etc/fstab
```

## Install unzip, htop, nmap, sysstat, psmisc, fail2ban
```bash
yum install unzip htop nmap sysstat psmisc fail2ban ntp
```

## Configure fail2ban and Enable it on Startup
```bash
sudo systemctl enable fail2ban
```
make `jail.local` config file
```bash
sudo nano /etc/fail2ban/jail.local
```
and paste in it
```bash
[DEFAULT]
# Ban hosts for one hour:
bantime = 3600

# Override /etc/fail2ban/jail.d/00-firewalld.conf:
banaction = iptables-multiport

[sshd]
enabled = true
```
and restart fail2ban
```bash
sudo systemctl restart fail2ban
```

## Change timezone
```bash
sudo timedatectl set-timezone Europe/Athens
```

## Enable NTP
```bash
systemctl enable ntpd
ntpdate pool.ntp.org
timedatectl set-ntp true
```

## Restart + Check Back Alive
(will need to re-log putty)
```bash
sudo shutdown -r now
```

## Verify everything works
SELinux status should return `disabled`
```bash
sestatus
```
Swap size should return around 4Gb
```bash
swapon -s
```
fail2ban should be active in processes
```bash
systemctl is-active fail2ban
```
fail2ban should return at least 1 jail
```bash
sudo fail2ban-client status
```
time should agree with local time (Athens, GR)
```bash
date
```
NTP should be enabled
```bash
timedatectl
```

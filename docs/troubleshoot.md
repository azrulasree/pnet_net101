# Troubleshoot PNETLab

## Guacamole 404 Error

```shell
wget https://labhub.eu.org/api/raw/?path=/UNETLAB%20I/upgrades_pnetlab/bionic/Testing/pnetlab-guacamole/pnetlab-guacamole_4.0.0-6_amd64.deb --content-disposition
dpkg -i pnetlab-guacamole_4.0.0-6_amd64.deb
```

---

## "Please Synchronize Your Time"

```shell
# Step 1: Login with root
# Step 2: Set timezone to UTC
timedatectl set-timezone UTC
# Step 3: Set date
date -s '2023-05-10T09:48:34'
```

---

## pnet0 No IP

Reference: https://divelement.ro/fix-eve-ng-no-ip-address-on-interface-pnet0/

---

## Can't Login — HDD Full

```shell
df -h
```

Extend disk: https://askubuntu.com/questions/1417938/ubuntu-does-not-use-full-disk-space-how-to-extend

---

## Device Starts and Stops Immediately

- Enable Virtualization in BIOS and VM settings
- Disable Hyper-V
- Disable Core Isolation
- System > System Settings > ishare2 relicense

---

## Can't Run QEMU

- Enable VT-x in BIOS
- Check in VM settings

```shell
sudo -i
kvm-ok
grep -cw vmx /proc/cpuinfo
uname -a
```

---

## Reinstall MySQL

```shell
sudo ln -s /etc/apparmor.d/usr.sbin.mysqld /etc/apparmor.d/disable/
sudo apparmor_parser -R /etc/apparmor.d/usr.sbin.mysqld
sudo apt install mysql-server
```

---

## 30-Day License

```shell
show license status
# supply .yml files
```

---

## Image Not Shown in Node After Added

```shell
ishare2 installed qemu
cd /opt/unetlab/html/templates/intel
# fix permissions + clear browser cache
```

---

## Generate IOL iourc License

```shell
cd /opt/unetlab/addons/iol/bin/
python CiscoIOUKeygen.py > iourc
```

Or via ishare2:
```shell
ishare2 relicense
```

Notes:
- Install python2 if needed
- If keygen not present, use the attached file

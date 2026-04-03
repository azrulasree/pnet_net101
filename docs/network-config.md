# Network Config

> **IMPORTANT:** On EVE-NG/PNETLab systems, `/etc/network/interfaces` **OVERRIDES Netplan completely**.

## Edit Interface Config

```shell
nano /etc/network/interfaces
```

## Default Config

```
# The primary network interface
iface eth0 inet manual
auto pnet0
iface pnet0 inet dhcp
    bridge_ports eth0
    bridge_stp off
```

## Full Default (all bridges)

```
auto lo
iface lo inet loopback

iface eth0 inet manual
auto pnet0
iface pnet0 inet dhcp
    pre-up ip link set dev eth0 up
    bridge_ports eth0
    bridge_stp off

iface eth1 inet manual
auto pnet1
iface pnet1 inet manual
    bridge_ports eth1
    bridge_stp off

# ... (repeat for eth2-eth9)

auto natmac
iface natmac inet manual
    pre-up ip link add natmac address 00:01:01:01:01:01 type dummy

auto nat0
iface nat0 inet static
    bridge_ports natmac
    bridge_stp off
    address 10.0.137.254
    netmask 255.255.255.0
    postup ip link set nat0 address 00:aa:aa:aa:aa:aa
    up service udhcpd restart
```

## Static IP Config (example)

```
auto lo
iface lo inet loopback

# pnet0 (eth0) - Cloud0 - NAT (vmnet8)
iface eth0 inet manual
auto pnet0
iface pnet0 inet static
    pre-up ip link set dev eth0 up
    bridge_ports eth0
    bridge_stp off
    address 10.10.80.12
    netmask 255.255.255.0
    gateway 10.10.80.1
    dns-nameservers 8.8.8.8 1.1.1.1

# pnet1 (eth1) - Cloud1 - MgmtNet
iface eth1 inet manual
auto pnet1
iface pnet1 inet static
    bridge_ports eth1
    bridge_stp off
    address 10.10.30.12
    netmask 255.255.255.0

# pnet2 (eth2) - Cloud2 - ProdNet
iface eth2 inet manual
auto pnet2
iface pnet2 inet static
    bridge_ports eth2
    bridge_stp off
    address 10.10.20.12
    netmask 255.255.255.0
```

Save: `CTRL+O` then `CTRL+X`

```shell
/etc/init.d/networking restart
reboot
```

## Add DNS

```
iface pnet0 inet dhcp
    dns-nameservers 8.8.8.8
    bridge_ports eth0
    bridge_stp off
```

Or:
```shell
echo 'nameserver 8.8.8.8' >> /etc/resolvconf/resolv.conf.d/head
echo 'nameserver 1.1.1.1' >> /etc/resolvconf/resolv.conf.d/head
resolvconf --enable-updates && resolvconf -u && rm -f /etc/netplan/* || true
/etc/init.d/networking restart
```

## Change HTTP Port

```shell
vi /etc/apache2/ports.conf
# Comment out: #Listen 80
/etc/init.d/apache2 restart
```

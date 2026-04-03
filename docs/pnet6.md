# PNETLab 6 Installation

Reference: https://www.youtube.com/watch?v=_Qt1-4aXt5Y

## Requirement
- Ubuntu 20.04

## Fresh Installation

```shell
sudo -i
echo "deb [trusted=yes] http://repo.pnetlab.com ./" | tee -a /etc/apt/sources.list
apt-get update
apt-get install pnetlab
```

## 1-Command Installation

```shell
sudo su
bash -c "$(curl -sL https://labhub.eu.org/api/raw/?path=/UNETLAB%20I/upgrades_pnetlab/Focal/install_pnetlab_v6.sh)"
```

Or via curl:
```bash
curl https://drive.labhub.eu.org/0:/upgrades_pnetlab/Focal/install_pnetlab_v6.sh | bash
```

## Offline Installation

Guide: https://www.youtube.com/watch?v=GjS2aHY-V7Q

1. Download from: https://drive.labhub.eu.org/0:/upgrades_pnetlab/
2. Unzip
3. Edit the `.sh` file
4. Create `/opt/pnet` and set ownership:
```bash
mkdir pnet
chown pnet sysadmin
```
5. Upload to `/opt/pnet` via WinSCP
6. Make executable and run:
```bash
cd pnet
chmod +x install_pnet_v6.sh
./install_pnet_v6.sh
```

## Upgrade to Latest v6

```shell
# Check current version
cat /opt/unetlab/version

# Upgrade
curl -sSL "https://labhub.eu.org/api/raw/?path=/upgrades_pnetlab/focal/install_pnetlab_v6.sh" | bash
```

Or alternate:
```shell
curl -sSL https://drive.labhub.eu.org/upgrades_pnetlab/focal/install_pnetlab_v6.sh | bash
```

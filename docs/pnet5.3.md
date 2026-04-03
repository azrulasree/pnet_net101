# PNETLab 5.3 Installation

## Installation

1. Download the OVA PNETLab 4.2.10 from [pnetlab.com](https://pnetlab.com/pages/documentation?slug=install-PNETlab)
2. Update dependencies:
```bash
apt update
apt upgrade
```

## Upgrade to v5

```shell
bash -c "$(curl -sL https://labhub.eu.org/api/raw/?path=/UNETLAB%20I/upgrades_pnetlab/bionic/install_pnetlab_latest_v5.sh)"
```

Or testing version:
```shell
bash -c "$(curl -sL https://labhub.eu.org/api/raw/?path=/UNETLAB%20I/upgrades_pnetlab/bionic/install_pnetlab_v5_testing.sh)"
```

Or download and run manually:
```shell
wget --content-disposition -q --show-progress https://labhub.eu.org/api/raw/?path=/UNETLAB%20I/upgrades_pnetlab/bionic/install_pnetlab_v5_testing.sh
bash install_pnetlab_v5_testing.sh
```

## Alternate Upgrade Mirror

```bash
bash -c "$(curl -sL https://drive.labhub.eu.org/0:/upgrades_pnetlab/bionic/install_pnetlab_latest_v5.sh)"
```

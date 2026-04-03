# Templates / Images Config

## Image Locations

| Type | Path |
|---|---|
| IOL | `/opt/unetlab/addons/iol/bin` |
| QEMU | `/opt/unetlab/addons/qemu` |
| Dynamips | `/opt/unetlab/addons/dynamips` |
| Templates | `/opt/unetlab/html/templates` |

## Download Images via ishare2

```shell
ishare2 search [qemu|iol|name]
ishare2 pull [qemu|iol|dynamips] [image_number]
```

## Manual Download

```shell
cd /opt/unetlab/addons/iol/bin
wget https://drive.labhub.eu.org/0:/addons/iol/bin/i86bi_LinuxL2-AdvEnterpriseK9-M_152_May_2018.bin --content-disposition
```

## Remove IOL L2 File

Go to pnetlab directory and delete the `i86bi*.yml` file.

## Image List

| Product | Image Name | Username/Password | Notes |
|---|---|---|---|
| Huawei NE40 | huaweine40-ne40 | NA/NA | Recommended |
| Huawei CE12800 | ce12800 | no password | |
| Checkpoint | cspg-R81.10 | admin/admin123 | |
| Paloalto | paloalto-8.0.0 | admin/admin | new pw: P@ssw0rd |
| | paloalto-9-1-2 | admin/admin | OK |
| | paloalto-10.0.4-Pre-Licensed-Eval | | |
| Fortinet | fortinet-FGT-v7.0.3-build0237 | admin/NA | |
| ASA | asav 9.14(2)13 | | |
| | asav 9.19.1 | cisco123/NA | |
| Mikrotik | mikrotik-6.49 | admin/NA | |
| | mikrotik-7.6 | admin/NA | |
| SD-WAN | vmanage-19.2.3 / vtedge-19.2.2 / vtsmart-19.2.2 | admin/admin | change pw after |
| Windows | win-tiny10 | admin/admin | |
| Linux | linux-debian-10 | user/Test123 | |
| Nagios | nagios-5.4 | root/nagiosxi | GUI: nagiosadmin/apaponxboleh1 |
| IOL L2 | i86bi_linux_l2-adventerprisek9-ms.SSA.high_iron_20190423.bin | | Recommended L2 |
| IOL L3 | i86bi_linux-l3-adventerprisek9-15.5.2T.bin | | Recommended L3 |
| IOL L2 alt | i86bi_LinuxL2-AdvEnterpriseK9-M_152_May_2018.bin | | Community recommended |
| Nexus | nxosv9k-7.0.3.15.2 | admin/NA | |
| | nxosv9k-9500-9.3.9 | admin/NA | OK |
| IOS-XE | csr1000vng-17.03.04a | | OK |
| IOS-XR | xrv9k-7.3.3 / xrv9k-7.11.1 | | SP Lab - Segment Routing |
| | xrv-6.1.3 | | SP Lab - lower resources |

## Notes
- RAM options: 1024, 2048, 4096, 8192
- For ACI: requires dedicated Cisco Server
- VFP: 3vCPU + 4GB RAM per node
- VCP: 1vCPU + 1GB RAM per node

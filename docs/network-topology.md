# Network Topology

Configured with mgmt interface connecting all intranet.

## Interface Mapping

| MAC | NIC | PNETLab Virtual Interface | Network (GUI) | IP Address |
|---|---|---|---|---|
| 00:0C:29:69:A8:59 | eth0 (enp2s1 / ens33) | pnet0 | Cloud0 | 10.10.80.X/24 |
| 00:0C:29:69:A8:63 | eth1 (enp2s2 / ens34) | pnet1 | Cloud1 | 10.10.30.X/24 |
| 00:0C:29:69:A8:77 | eth2 (enp2s7 / ens39) | pnet2 | Cloud2 | 10.10.20.X/24 |

## Network Summary

- **Cloud0 / pnet0** — Internet/NAT (10.10.80.0/24)
- **Cloud1 / pnet1** — Management Network (10.10.30.0/24)
- **Cloud2 / pnet2** — Production Network (10.10.20.0/24)

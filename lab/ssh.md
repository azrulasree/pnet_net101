# SSH Configuration

## IOS-XE

```ios
hostname R1
ip domain-name khairi.com
crypto key generate rsa

username cisco privilege 15 password cisco

line vty 0 4
 login local
 transport input ssh

ip ssh version 2
ip ssh server algorithm encryption aes256-ctr aes192-ctr aes128-ctr
ip ssh server algorithm mac hmac-sha2-256 hmac-sha2-512
ip ssh server algorithm kex diffie-hellman-group-exchange-sha256 diffie-hellman-group14-sha256
```

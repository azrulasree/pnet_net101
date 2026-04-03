# Server Spec

## Workstation Spec
24 Core, 128GB RAM, 100GB SSD

## Useful Commands

```shell
ls -ltr
whoami                          # check user
cat /opt/unetlab/version        # see version
uname -a                        # processor architecture, hostname, kernel version
lsb_release -a                  # see distro
service tomcat9 status
service guacd status            # see guacamole status
more /etc/network/interfaces    # see interface settings
systemctl list-unit-files|grep resolved
hostname                        # see VM name
```

## Credentials

### Server
- username: `root`
- password: `pnet`

### Website
- **online**: registered account
- **offline**: `admin` / `pnet`

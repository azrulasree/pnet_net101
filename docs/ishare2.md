# ishare2

GitHub: https://github.com/ishare2-org/ishare2-cli

## Install

```shell
wget -O /usr/sbin/ishare2 https://raw.githubusercontent.com/pnetlabrepo/ishare2/main/ishare2 > /dev/null 2>&1 && chmod +x /usr/sbin/ishare2 && ishare2
```

## Commands

```shell
# Reconfigure
ishare2 config

# Test connectivity to Google and labhub drive
ishare2 test

# Upgrade
ishare2 upgrade
# choose option 1 or option 2

# Relicense
ishare2 relicense

# Search images
ishare2 search
ishare2 search [qemu|iol|name]

# Pull image
ishare2 pull [qemu|iol]

# List installed
ishare2 installed qemu
```

## Install GUI

```shell
sudo
pip install uvicorn
pip install jinja2
pip install fastapi
ishare2 gui install
ishare2 gui start
```

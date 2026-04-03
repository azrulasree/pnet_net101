# EVE-NG / PNETLab Windows Client

Install the EVE-NG Win Client Pack for a better experience — enables Putty, Wireshark, and SecureCRT integration.

Download: `EVE-NG-Win-Client-Pack-2.0.zip` — run the file and restart PC.

## WinSCP

Open WinSCP > New Session > SFTP > [eve ip] > save password

- username: `root`
- password: `eve`

## Wireshark via plink

Locate `plink.exe` (usually at `C:\Program Files\EVE-NG`):

```powershell
plink.exe root@192.168.1.26
y    # accept host key
# username: root, password: eve
```

Then in PNETLab: right-click router > capture interface.

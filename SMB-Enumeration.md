# Server Message Block (SMB)

## Enumeration
Performn a basic scan of the target SMB server.

- Query DC Name, Hostname and OS Version
```shell
crackmapexec smb 10.10.10.10
```
- List available Directory Shares
```shell
crackmapexec smb 10.10.10.10 --shares
```
If no shares are discovered, try NULL Session Authentication.

---

## Vulnerabilities and Attacks

### Null Session Authentication
```shell
crackmapexec smb 10.10.10.10 -u 'Null' -p '' --shares
```
OR
```shell
smbclient -N -L //10.10.10.10
```

If you are able to discover directory shares with read permissions, next you should connect to the share and look at it's contents. 

---

### Connecting to a Directory Share
```shell
smbclient -N //10.10.10.10/directory_share
```

### Download Files from a Directory Share
```shell
smb:> get filename.ext
```

# Server Message Block (SMB)

## Enumeration
Performn a basic scan of the target SMB server.

- Query DC Name, Hostname and OS Version
```shell
crackmapexec smb 10.10.10.10
```
- List available shares
```shell
crackmapexec smb 10.10.10.10 --shares
```

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

# Potential Privilege Escalation Paths

## Environment Variables
What is current set up as environment variables?
```
env || set
```

## Root Permissions
Non-root users may be allowed to perform some commands as root user.
Below commands will show permission granted to the current user by user or groups
```
sudo -l
```

### GTFOBins
Check [GTFOBins](gtfobins.github.io) for binaries that can be used to privilege escalate when configured to allow root permissions.

## Vulnerable Software
Command below return installed software, packages, and services with their versions.
```
dpkg -l
```

Sites like [ExploitDB](www.exploit-db.com) and the [Mitre CVE Database](cve.mitre.org) can be used to find vulnerable software versions.

## Passwords
There could be files with passwords stored in them.

```
grep -ri 'password' <directory>
```

Also check other similar regex:
```
pass
pw
...
```

## Weak File Permissions
Find all the files that the current user has write access to.
```
find / -type f -writable
```

Can also try to see what the current user can read.
```
find <dir> -type f -readable -not -path "/home/$(whoami)/*"
```

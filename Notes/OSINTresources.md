

## OSINT Anonymou persona

```bash
https://www.fakenamegenerator.com/
https://namso-gen.com/?tab=basic&network=random
https://www.thispersondoesnotexist.com/ - pictures
Privacy Cards: https://privacy.com/

```


## OSINT resources

```bash
https://osintframework.com/
https://i-intelligence.eu/uploads/public-documents/OSINT_Handbook_2020.pdf
https://start.me/p/DPYPMz/the-ultimate-osint-collection
https://docs.google.com/spreadsheets/d/18rtqh8EG2q1xBo2cLNyhIDuK9jrPGwYr9DI2UncoqJQ
https://cipher387.github.io/
```

## OSINT websites

```bash
# Multipurpose
https://shodan.io/
https://censys.io/
https://onyphe.io/
https://app.netlas.io/
https://hunter.how/
https://fofa.so/
https://fullhunt.io/
https://www.zoomeye.org/
https://www.criminalip.io/
https://leakix.net/
https://www.yougetsignal.com/
https://intelx.io/
https://pentest-tools.com/
https://gofindwhois.com/
https://gofindwho.com/
# Public info gathering

# Track website changes
https://visualping.io/
https://web.archive.org

# Companies info
https://opencorporates.com/companies

# Domain Recon
https://www.robtex.com/
https://centralops.net
https://viewdns.info/
https://phpinfo.me/domain
http://bgp.he.net/
https://bgpview.io/
https://suip.biz/
https://dnsdumpster.com/
https://www.whoxy.com/
http://ipv4info.com/
https://rapiddns.io/
https://myip.ms/
https://www.reversewhois.io/?
https://www.whoxy.com/reverse-whois/
https://reverse-whois.whoisxmlapi.com/api
https://host.io/dashboard
https://completedns.com/dns-history/
```
# Analytics
https://mmhdan.herokuapp.com/
https://publicwww.com/
https://intelx.io/tools?tab=analytics
https://dnslytics.com/reverse-analytics
https://builtwith.com/

# Mailserver blacklists
http://multirbl.valli.org/

# Verify emails
https://tools.emailhippo.com/

# Dark web exposure
https://immuniweb.com/radar/

# New acquisitions
https://crunchbase.com/

# Public APIs
https://www.postman.com/explore/
https://rapidapi.com/

# APIs Recon
https://serene-agnesi-57a014.netlify.app/

# Exif Data 
https://exif-viewer.com

## General / AIO

```bash
# https://github.com/OWASP/Amass
# Get ASN
amass intel -org "whatever"
# Reverse whois
amass intel -active -asn NUMBER -whois -d domain.com
# SSL Cert Grabbing
amass enum -active -d example.com -cidr IF.YOU.GOT.THIS/24 -asn NUMBER

# https://github.com/smicallef/spiderfoot
spiderfoot -s domain.com

# https://github.com/j3ssie/Osmedeus
python3 osmedeus.py -t example.com

# https://github.com/thewhiteh4t/FinalRecon
python3 finalrecon.py --full https://example.com

# https://github.com/laramies/theHarvester
theHarvester -d domain.com -b all

# https://github.com/lanmaster53/recon-ng
recon-ng
```
## Whois/Registrant Tools

```bash
# https://github.com/jpf/domain-profiler
./profile target.com

# Standard whois tool
whois

# Whoxy api
# https://www.whoxy.com/
# Whoxy clients
# https://github.com/MilindPurswani/whoxyrm
# https://github.com/vysecurity/DomLink

# Registrant's domains related
# https://github.com/harleo/knockknock
knockknock -n "companyORregistrant" -p

# Bulk whois
# https://github.com/melbadry9/WhoEnum
```
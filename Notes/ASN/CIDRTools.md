## ASN/CIDR Tools

```bash
# Company string name to CIDR
# https://github.com/dhn/spk
spk -json -s "Google"

# Versatile tool with multiple input options and output formats
# https://github.com/projectdiscovery/asnmap
asnmap -i 1.3.3.7 -org GOOGLE -d facebook.com,twitter.com -a AS394161

# https://github.com/nitefood/asn
asn -n 8.8.8.8

# https://github.com/j3ssie/metabigor
echo "company" | metabigor net --org
echo "ASN1111" | metabigor net --asn

# https://github.com/yassineaboukir/Asnlookup
python asnlookup.py -m -o <Organization>

# https://github.com/harleo/asnip
asnip -t domain.com -p

# https://github.com/projectdiscovery/mapcidr
echo 10.10.10.0/24 | mapcidr

# https://github.com/eslam3kl/3klector
python 3klector.py -t company

# https://github.com/SpiderLabs/HostHunter
python3 hosthunter.py targets.txt

# Website (with API)
https://asnlookup.com/
```
## Credentials leaks

```bash
# pwndb
# https://github.com/davidtavarez/pwndb
python3 pwndb.py --target asd@asd.com

# Websites
https://link-base.org/index.php
http://xjypo5vzgmo7jca6b322dnqbsdnp3amd24ybx26x5nxbusccjkm4pwid.onion/
http://pwndb2am4tzkvold.onion
https://weleakinfo.to/
https://www.dehashed.com/search?query=
https://haveibeenpwned.com
https://breachchecker.com
https://vigilante.pw/
https://leak.sx/
https://intelx.io
https://search.illicit.services/
https://breachdirectory.org/

breachdirectory.org + (hashes.com || md5decrypt.net || crackstation.net)# Nice combination

# Check hashes with this tool
https://github.com/jackrendor/jhf
```
## Email tools

```bash
# https://github.com/SimplySecurity/SimplyEmail
./SimplyEmail.py

pip3 install mailspoof
sudo mailspoof -d domain.com

# Test email spoof
https://emkei.cz/

# Find emails in an org
https://hunter.io
https://snov.io/email-finder
https://app.snov.io/domain-search
https://hunter.io/

# https://github.com/sham00n/buster
buster -e target@example.com

# https://github.com/m4ll0k/Infoga
python infoga.py

# https://github.com/martinvigo/email2phonenumber
python email2phonenumber.py scrape -e target@email.com

# https://github.com/jkakavas/creepy/

# https://github.com/Josue87/EmailFinder
emailfinder -d domain.com

# https://github.com/laramies/theHarvester
python3 theHarvester.py -d domain.com -b "linkedin"
```

## GIT tools

```bash
# https://github.com/obheda12/GitDorker
python3 GitDorker.py -tf TOKENSFILE -q tesla.com -d dorks/DORKFILE -o target

# https://github.com/dxa4481/truffleHog
trufflehog https://github.com/Plazmaz/leaky-repo
trufflehog --regex --entropy=False https://github.com/Plazmaz/leaky-repo

# https://github.com/eth0izzle/shhgit
shhgit --search-query AWS_ACCESS_KEY_ID=AKIA

# https://github.com/d1vious/git-wild-hunt
python git-wild-hunt.py -s "extension:json filename:creds language:JSON"

# https://shhgit.darkport.co.uk/

# GitLab (API token required)
# https://github.com/codeEmitter/token-hunter
./token-hunter.py -g 123456
```

## Metadata

```bash
# https://github.com/Josue87/MetaFinder
metafinder -d "domain.com" -l 10 -go -bi -ba -o united
```

## Social Media

```bash
# Twitter
# https://github.com/twintproject/twint
twint -u username

# Google account
# https://github.com/mxrch/ghunt
python hunt.py myemail@gmail.com

# Instagram
# https://github.com/th3unkn0n/osi.ig
python3 main.py -u username

# Public GDrive docs
https://www.dedigger.com/#gsc.tab=0

# Websites
emailrep.io # Accounts registered by email
tinfoleak.com # Twitter
mostwantedhf.info # Skype
searchmy.bio # Instagram
search.carrot2.org # Results grouped by topic
boardreader.com # forums
searchcode.com # search by code in repositories
swisscows.com # semantic search engine
publicwww.com # search by source page code
psbdmp.ws # search in pastebin
kribrum.io # social-media search engine
whatsmyname.app
```
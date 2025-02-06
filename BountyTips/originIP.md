** How to find the origin Ip of website behind waf ** 

- check domain using ping command to view waf ip
- check via wafwoof ie `wafw00f URL` to check whether waf is available or not.


`dnsrecon -d domain`
- performs reverse dns lookups 

shodan dork to find related domain infromation
- `Ssl.cert.subject.CN:'example.com' 200`   
- once you find an ip and suspect waf use wafw00f command to view whether there is a waf or not.
- shodan command line 
`shodan search Ssl.cert.subject.CN:'example.com' 200 --fields ip_str  | httpx `


Favicon hash method
find favicon either via 
- https://favicons.teamtailor-cdn.com/
- ading the -favicon to `httpx -favicon`
- after getting the hash use shodan dork `http.favicon.hash:-688604782` 
- https://favicon-hash.kmsec.uk/  - use this site as well. has shodan cencys and virustotal search

checking ip history of the domain using
- https://viewdns.info/ 
- one has to verify ip belongs to the starget

checking the spf record of the domain
- https://mxtoolbox.com/SuperTool.aspx#

checking domain in security trails and clicking on historical records to see ips

checking cencys 
- https://search.censys.io/search
- in search bar input domain name of target

checking on FOFA
- https://en.fofa.info/
- in search bar input domain name of target
- you can also filter with site favicon hash

checking on Zoomeye
- https://www.zoomeye.ai/
- https://www.zoomeye.ai/gpt
- in search bar input domain name
- you can also filter by favicon hash

checking via virustotal
- `curl -s "https://www.virustotal.com/vtapi/v2/domain/reprot?domain=example.com&apikey=APIKEY"`

checking alienvault
- `curl -s https://otx.alienvault.com/api/v1/indicators/hostname/domain.com/url_list?limit=500&page=1| jq  -r '.url_list[]?.result?.urlworker?.ip // empty'`

checking from urlscan.io
- `curl -s https://urlscan.io/api/v1/search/q=domain:example.com&size=10000`
- use the ui web search if api doesnt work


If you find an ip and it doesnt resolve or something like that 
add it to the etc/hosts file and recheck the site
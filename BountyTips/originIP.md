** How to find the origin Ip of website behind waf ** 

- check domain using ping command to view waf ip
- check via wafwoof ie `wafw00f URL` to check whether waf is available or not.


`dnsrecon -d domain`
- performs reverse dns lookups 

shodan dork to find related domain infromation
- `Ssl.cert.subject.CN:'example.com' 200`   
- once you find an ip and suspect waf use wafw00f command to view whether there is a waf or not.

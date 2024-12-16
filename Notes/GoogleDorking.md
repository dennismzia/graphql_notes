## Google Dorks for Bug Bounty

A list of Google Dorks for Bug Bounty, Web Application Security, and Pentesting

## understanding

• \- (minus)—The dash is used to negate a term from the search results. For instance,
cybersecurity -Cisco will provide results that contain the word cybersecurity but
remove all entries that contain Cisco.

• OR—This is a conditional operator to provide results of either one term or the other. For
example, cybersecurity OR networking will provide results containing either the word cybersecurity or networking in them.

• AND—This conditional operator is used to provide results that include two terms. For instance,
football AND england will return results that contain both keywords.

• intitle:—This operator is used to search for title pages that contain a specific term(s). For
instance, intitle: administrator will search for all websites where administrator is found in the title and return these results.

• inurl:—This operator searches for URLs that contain a specific keyword. For example,
inurl:security provides all URLs that contain the keyword security.

• intext:—This operator enables Google to examine whether a specific keyword is found
within the body of a website and provide results for those websites only. For example,
intext:cryptocurrency provides results of web pages that contain the word cryptocurrency
within their body.

• ext:/ filetype:—These operators are used to specify a file extension. For instance,
cybersecurity filetype:pdf will provide results that contain the word cybersecurity
and a PDF file.

• site:—This operator is used to provide results for a specific domain name. For example,
site:microsoft.com will provide results for microsoft.com only.

• before: yyyy-mm-dd—This operator filters results before a particular time. This is useful
if you’re interested in finding results or data that was published before a certain time.

• after: yyyy-mm-dd—This operator filters results after a particular time. This is useful if
you’re interested in finding results or data that was published after a certain time.

• \* (asterisk)—This operator is used as a wildcard to match any keyword. For example, cyber

-   will provide results showing anything that starts with cyber.

[Live Tool](https://taksec.github.io/google-dorks-bug-bounty/)

**Broad domain search w/ negative search**

`site:example.com -www -shop -share -ir -mfa`

**PHP extension w/ parameters**

`site:example.com ext:php inurl:?`

**API Endpoints**

`site:example[.]com inurl:api | site:*/rest | site:*/v1 | site:*/v2 | site:*/v3`

**Juicy Extensions**

```
site:"example[.]com" ext:log | ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess | ext:json
```

**High % inurl keywords**

```
inurl:conf | inurl:env | inurl:cgi | inurl:bin | inurl:etc | inurl:root | inurl:sql | inurl:backup | inurl:admin | inurl:php site:example[.]com
```

**Server Errors**

```
inurl:"error" | intitle:"exception" | intitle:"failure" | intitle:"server at" | inurl:exception | "database error" | "SQL syntax" | "undefined index" | "unhandled exception" | "stack trace" site:example[.]com
```

**XSS prone parameters**

`inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:example.com`

**Open Redirect prone parameters**

`inurl:url= | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= inurl:& inurl:http site:example.com`

**SQLi Prone Parameters**

`inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com`

**SSRF Prone Parameters**

```
inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain= | inurl:page= inurl:& site:example.com
```

**LFI Prone Parameters**

````
inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= |inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com
```

**RCE Prone Parameters**

````

inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read= | inurl:ping= inurl:& site:example.com

```

**File upload endpoints**

`site:example.com ”choose file”`

**API Docs**

`inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api-explorer site:"example[.]com"`

**Login Pages**

`inurl:login | inurl:signin | intitle:login | intitle:signin | inurl:secure site:example[.]com`

**Sensitive Documents**

`site:example.com ext:txt | ext:pdf | ext:xml | ext:xls | ext:xlsx | ext:ppt | ext:pptx | ext:doc | ext:docx`
`intext:“confidential” | intext:“Not for Public Release” | intext:”internal use only” | intext:“do not distribute”`

**Sensitive Parameters**

`inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example[.]com`

**Adobe Experience Manager (AEM)**

```

inurl:/content/usergenerated | inurl:/content/dam | inurl:/jcr:content | inurl:/libs/granite | inurl:/etc/clientlibs | inurl:/content/geometrixx | inurl:/bin/wcm | inurl:/crx/de site:example[.]com

```

**Disclosed XSS and Open Redirects**

`site:openbugbounty.org inurl:reports intext:"example.com"`

**Code Leaks**

`site:pastebin.com "example.com"`

`site:jsfiddle.net "example.com"`

`site:codebeautify.org "example.com"`

`site:codepen.io "example.com"`

**Cloud Storage**

`site:s3.amazonaws.com "example.com"`

`site:blob.core.windows.net "example.com"`

`site:googleapis.com "example.com"`

`site:drive.google.com "example.com"`

`site:dev.azure.com "example[.]com"`

`site:onedrive.live.com "example[.]com"`

`site:digitaloceanspaces.com "example[.]com"`

`site:sharepoint.com "example[.]com"`

`site:s3-external-1.amazonaws.com "example[.]com"`

`site:s3.dualstack.us-east-1.amazonaws.com "example[.]com"`

`site:dropbox.com/s "example[.]com"`

`site:box.com/s "example[.]com"`

`site:docs.google.com inurl:"/d/" "example[.]com"`


- further reading
https://www.exploit-db.com/google-hacking-database.
```

* this returns more domains than normal 
```
site:*<*.target.*

site:*<-*.target.*

site:*>*.target.*

site:*->*.target.*

site:*<->*.target.*
```
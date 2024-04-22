# miscellaneous notes

-   searching web archive

```html
http://web.archive.org/cdx/search/cdx?url=google.com%2Fapi%2F*&output=text&fl=original&collapse=urlkey&from=
```

-   Uncontrolled resource consumption

Azure shared access signature ie sas token if it doesnt have the appropriate expiration dat e or limit then attack here is to download and big blob (data) like 200GB and download it 10 times that will cause the usage to go up to 2TB.

- subdomain enumeration idea. looking for staging test or dev sites always helps

```js 
https://github.com/netsecurity-as/subfuz/blob/master/subdomain_megalist.txt 
```

```bash
ffuf -w /subdomain_megalist.txt -u 'https://adminFUZZ.Target.com' -c  -t 350 -mc all  -fs 0

# example
admin-FUZZ.target.com E.G: admin-stg.target.com
FUZZ-admin.target.com E.G: cert-admin.target.com
adminFUZZ.target.com  E.G: admintest.target.com
FUZZadmin.target.com  E.G  testadmin.target.com
admin.FUZZ.target.com E.G: admin.dev.target.com

```

- cencys
```js
1. openup https://search.censys.io/
2.Search the keyword with virtual host only-
`(services.tls.certificates.leaf_data.names: anywebsite.com) and services.http.response.status_code=”200"`

```

url would look like
```js
https://youraccount.blob.core.windows.net/?restype=container&comp=list&sv=2022-11-02&se=2023-05-24T09:51:36Z&sp=r&sig=<signature>

```

```js
console.log(__BUILD_MANIFEST.sortedPages) // all paths for Next.js websites

window.__NEXT_DATA__.props.pageProps //returns back the data object passed from the server-side
```

CORS* Burp Extension. 
scans for cors misconfigurations.

### fuzzing for xss
I initiated <mark>fuzzing</mark>on the <mark>sign-up</mark> page using a wordlist of ==JavaScript variable names==.

During this process, I observed that a parameter name `appURL` was being ==reflected== within a script tag.



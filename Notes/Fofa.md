# recon techniques on fofa 

FOFA dorks

`domain="example.com"`
- with favicon hash
`domain="example.com" && icon_hash="xxxxxxxxxx"`

- 1️⃣ HTTPS ports apart from 443

`domain="example.com" && protocol="https" && port!="443"`
`domain="example.com" && protocol="https" && port!="443" && port!="80"`

- 3️⃣ Cloud Buckets
`domain="example.com" && body="ListBucketResult"`

- 4️⃣ Metrics Endpoints or Similar to it
```
body="http_request_duration_seconds_sum"
body="http_requests_in_flight"
body="http_responses_total"
body="http_request_duration_seconds_bucket"
body="http_request_duration_seconds_count"
body="flask_http_request_duration_seconds_sum"
body="python_gc_objects_uncollectable_total"
body="process_virtual_memory_bytes"
body="process_resident_memory_bytes"
body="http_request_duration_highr_seconds_bucket"
body="kasiopea_assignment_total"
body="by_path_counter_total"


#combine with below using && operator
body="GET"
body="POST"
body="PUT"
body="/api"
body="/auth"
body="password"
body="security"
body="roles"
body="groups"
body="/v1"
body="/v2"
domain="example.com"


#extras
body="ghc_gcdetails_elapsed_seconds"
body="ghc_gcdetails_par_max_copied_bytes"
body="ghc_max_mem_in_use_bytes"
body="ghc_gcs_total"
```

- 5️⃣ Register
`body="register" && body="login" && domain="example.com"`

- 6️⃣ API Endpoints
`body="/api/v1" && domain="example.com"`
`body="/api/v2" && domain="example.com"`

- 7️⃣ Admin Endpoints
`body="/admin" && domain="example.com"`

-8️⃣ Information Disclosure
`body="any file name that leads to info disc" && domain="example.com"`
`body="config.txt" && domain="example.com"`

- 9️⃣ API Keys in JS Files

```
body="any_api_key_name_you_know" && domain="example.com"

#example for algolia api key
body="algolia_api_key" && domain="example.com"
body="algolia_application_id" && domain="example.com"
```

- WebSockets
```
body="new WebSocket" && domain="example.com"  

#secure websocket (wss://)
body="new WebSocket" && body="wss://" && domain="example.com"

#insecure websocket (ws://)
body="new WebSocket" && body="ws://" && domain="example.com"
```

- Cloudflare R2 Buckets
```
body="r2.dev" && domain="example.com"
body="r2.cloudflarestorage.com" && domain="example.com"

#you can combine with any other sensitive keywords you like
&& body="admin"
&& body="internal"
&& body="private"
&& body="secret"
&& body="companyname"
```

- GraphQL

```
body="graphql" && domain="example.com"
body="graphql" && body="query {" && domain="example.com"
body="graphql" && body="__typename" && domain="example.com"
body="graphql" && body="mutation" && domain="example.com"
```
- JavaScript FETCH API

```
body="fetch(" && domain="example.com"
body="fetch(" && body="/api/v1" && domain="example.com"
body="fetch(" && body="/api/v2" && domain="example.com"
body="fetch(" && body="/admin" && domain="example.com"
body="fetch(" && body="any_keyword_you_like" && domain="example.com"
```

- Juicy JavaScript Variables (E.g. Hex)
- useful for finding obfuscated code 
```
body="var _0x" && domain="example.com"
body="u006" && domain="example.com"
body="u007" && domain="example.com"
...
...
body="u00__" && domain="example.com"
```

-  Salesforce Endpoints
```
#Lightning endpoint
body="lightning.force.com" && domain="example.com"
```

- FireBaseApp
`body="firebaseapp" && domain="example.com"`

- ASN Enumeration
First, find the ASN number using [BGP](https://bgp.tools/) tools

```
#fofa asn dork
asn="number"
asn="AS...."
```

- Cloud Service Assets
```
is_cloud=true && domain="example.com"

#negative filter (remove cloud assets from results)
is_cloud=false && domain="example.com"
```
-  Status Codes
```
status_code="enter_any_status_code_here" && domain="example.com"

#403 forbidden
status_code="403" && domain="example.com"
```

- certificates
`cert.subject.cn="domain.com"`

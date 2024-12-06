## General bounty infromation and tips 

* do not be intimidated with public or private programs which has many hunters 

- for platform programs look at the hactivity section and disclosed reports.
- here you can find bypasses or ideas or more infromation on the app.
- you can also look at the report and try to find a bypass.

link to xss notes and techniques
- https://x.com/nav1n0x/status/1860044537932251225?t=FireSNfXHDVfaszce9J14Q&s=08


`
Vulnerability: Exposed Sentry Auth Token in JavaScript File or any where

Description:
A Sentry authentication token was found exposed in a JavaScript file, allowing access to:

Projects (view and delete capabilities).
Members (team roles and permissions).
Organizations (entire organizational structure).
Impact:
Full access to sensitive project data.
Ability to delete critical projects, posing significant risks to the organization.
Lesson:
Sentry tokens are highly sensitive and must never be hardcoded or exposed publicly.
Developers should use environment variables or secure storage to protect these tokens.
Notes:
Such issues seem to be increasingly common due to insecure development practices.
Always review public code repositories for potential token leaks.
`


- listing organisations
`curl -H 'Authorization: Bearer Auth_Token' sentry.io/api/0/organizations/`
- Listing Projects
`curl -H 'Authorization: Bearer Auth_Token' sentry.io/api/0/projects/ `
-Listing members
`curl -H 'Authorization: Bearer Auth_Token' sentry.io/api/0/organization/{memberID}/members`
- Deleting projects
`curl https://sentry.io/api/0/projects/{ID}/{project_id_or_slug}/  -H 'Authorization: Bearer Auth_Token'  -X DELETE`


* sensitive exposure
  - Add the file `appsettings.json` to your wordlist, and you might discover some juicy data. Enjoy! 
  - settings and keys such as client secrets were exposed
  
* cache poisoning
  - For cache poisoning bugs in Varnish, sending a Fastly-Key: 1 or Fastly-Debug: 1 header can sometimes reveal the cache key.

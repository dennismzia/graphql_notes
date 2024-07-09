## Manual

**1. Simple search**

At first, you should just simply search your target like xyz.com to understand their repo architecture how many repos, commits, and what kind of languages are found stuff like that.

**2. Sort**

Use sort: Recently Indexed to see the latest code result. Not Best Match option because old credentials may not be working now especially 4–5 years old on the other hand company also prefer the latest one.

**3. Dorks**

This is the main thing for github recon. In my suggestion, you can start with some basic dorks fast.

Here are some basic dorks!

```
api_key
“api keys”
authorization_bearer:
oauth
auth
authentication
client_secret
api_token:
“api token”
client_id
password
user_password
user_pass
passcode
client_secret
secret
password hash
OTP
user auth
#Some of the mine which I use generally

remove password
root
admin
log
trash
token
FTP_PORT
FTP_PASSWORD
DB_DATABASE=
DB_HOST=
DB_PORT=
DB_PASSWORD=
DB_PW=
DB_USER=
number
```

**3. Language**

Use github dorks with language to get more effective result.

```
like: language:shell username
language:sql username
language:python ftp
language:bash ftp
```

**4. Whildcard**

Use *(wildcard)for more result because sometime targeted website had .com or .net etc.In this case if you specify your github search like `xyz.com` then you may miss something of .net

You can also use `*(wildcard) like *.xyz.com`.

**5. URL**

You should also check URL (which looks important on your eyes)because some of the URL contains some important document like pdf ,ppt,xls file which may contain sensitive info.

> (you can simple this with google dorks like `site:xxyz.com ext:doc | ext:docx | ext:odt | ext:pdf | ext:rtf | ext:sxw | ext:psw | ext:ppt | ext:pptx | ext:pps | ext:csv | ext:txt | ext:html | ext:php | ext:xls`)

I said it because I found xls file on some website by doing this which contains user's details.

You can find some useful google dorks in my github repo.

**6. NOT**

Use NOT to filter your github search and get exact information from github ocean. like: xyz.com filename:prod.exs NOT prod.secret.exs.

**7. Social Media**

Follow the developers and employees of your target on social media. They can do stuff like leak teams links that are open, leak feature releases, leak acquisitions ect.

**8. Some useful Github dorks:**

```
dotfiles
filename:sftp-config.json password
filename:.s3cfg
filename:config.php dbpasswd
filename:.bashrc password
filename:.esmtprc password
filename:.netrc password
filename:_netrc password
filename:.env MAIL_HOST=smtp.gmail.com
filename:prod.exs NOT prod.secret.exs
filename:.npmrc _auth
filename:WebServers.xml
filename:sftp-config.json
filename:.esmtprc password
filename:passwd path:etc
filename:prod.secret.exs
filename:sftp-config.json
filename:proftpdpasswd
filename:travis.yml
filename:vim_settings.xml
filename:sftp.json path:.vscode
filename:secrets.yml password
extension:sql mysql dump
extension:sql mysql dump
extension:sql mysql dump password
extension:pem private
extension:ppk private
```

## Automation:

The manual way is best for finding sensitive info from Github. But if you want to automate this process then I suggest you for [GitDorker](https://github.com/obheda12/GitDorker). While GitHub hunting sometimes I also use this tool.Though it is a bit slow because to prevent rate limits Gitdocker sends 30 requests per minute. But it gives you much fewer false-positive results than other tools.

Also, you can use this tool that gave me amazing results.

```
$ git clone https://github.com/obheda12/GitDorker
$ python3 GitDorker.py -tf ~/Tools/.github_tokens -q united.com -p -ri -d Dorks/medium_dorks.txt
```

## Dorks List

```
".mlab.com password"
"access_key"
"access_token"
"amazonaws"
"api.googlemaps AIza"
"api_key"
"api_secret"
"apidocs"
"apikey"
"apiSecret"
"app_key"
"app_secret"
"appkey"
"appkeysecret"
"application_key"
"appsecret"
"appspot"
"auth"
"auth_token"
"authorizationToken"
"aws_access"
"aws_access_key_id"
"aws_key"
"aws_secret"
"aws_token"
"AWSSecretKey"
"bashrc password"
"bucket_password"
"client_secret"
"cloudfront"
"codecov_token"
"config"
"conn.login"
"connectionstring"
"consumer_key"
"credentials"
"database_password"
"db_password"
"db_username"
"dbpasswd"
"dbpassword"
"dbuser"
"dot-files"
"dotfiles"
"encryption_key"
"fabricApiSecret"
"fb_secret"
"firebase"
"ftp"
"gh_token"
"github_key"
"github_token"
"gitlab"
"gmail_password"
"gmail_username"
"herokuapp"
"internal"
"irc_pass"
"JEKYLL_GITHUB_TOKEN"
"key"
"keyPassword"
"ldap_password"
"ldap_username"
"login"
"mailchimp"
"mailgun"
"master_key"
"mydotfiles"
"mysql"
"node_env"
"npmrc _auth"
"oauth_token"
"pass"
"passwd"
"password"
"passwords"
"pem private"
"preprod"
"private_key"
"prod"
"pwd"
"pwds"
"rds.amazonaws.com password"
"redis_password"
"root_password"
"secret"
"secret.password"
"secret_access_key"
"secret_key"
"db_password"
"db_username"
"dbpasswd"
"dbpassword"
"dbuser"
"dot-files"
"dotfiles"
"encryption_key"
"fabricApiSecret"
"fb_secret"
"firebase"
"ftp"
"gh_token"
"github_key"
"github_token"
"gitlab"
"gmail_password"
"gmail_username"
"herokuapp"
"internal"
"irc_pass"
"JEKYLL_GITHUB_TOKEN"
"key"
"keyPassword"
"ldap_password"
"ldap_username"
"login"
"mailchimp"
"mailgun"
"master_key"
"mydotfiles"
"mysql"
"node_env"
"npmrc _auth"
"oauth_token"
"pass"
"passwd"
"password"
"passwords"
"pem private"
"preprod"
"private_key"
"prod"
"pwd"
"pwds"
"rds.amazonaws.com password"
"redis_password"
"root_password"
"secret"
"secret.password"
"secret_access_key"
"secret_key"
[WFClient] Password= extension:ica
access_key
bucket_password
dbpassword
dbuser
extension:avastlic "support.avast.com"
extension:bat
extension:cfg
extension:env
extension:exs
extension:ini
extension:json api.forecast.io
extension:json googleusercontent client_secret
extension:json mongolab.com
extension:pem
extension:pem private
extension:ppk
extension:ppk private
extension:properties
extension:sh
extension:sls
extension:sql
extension:sql mysql dump
extension:sql mysql dump password
extension:yaml mongolab.com
extension:zsh
filename:.bash_history
filename:.bash_history DOMAIN-NAME
filename:.bash_profile aws
filename:.bashrc mailchimp
filename:.bashrc password
filename:.cshrc
filename:.dockercfg auth
filename:.env DB_USERNAME NOT homestead
filename:.env MAIL_HOST=smtp.gmail.com
filename:.esmtprc password
filename:.ftpconfig
filename:.git-credentials
filename:.history
filename:.htpasswd
filename:.netrc password
filename:.npmrc _auth
filename:.pgpass
filename:.remote-sync.json
filename:.s3cfg
filename:.sh_history
filename:.tugboat NOT _tugboat
filename:_netrc password
filename:apikey
filename:bash
filename:bash_history
filename:bash_profile
filename:bashrc
filename:beanstalkd.yml
filename:CCCam.cfg
filename:composer.json
filename:config
filename:config irc_pass
filename:config.json auths
filename:config.php dbpasswd
filename:configuration.php JConfig password
filename:connections
```

```
filename:connections.xml
filename:constants
filename:credentials
filename:credentials aws_access_key_id
filename:cshrc
filename:database
filename:dbeaver-data-sources.xml
filename:deployment-config.json
filename:dhcpd.conf
filename:dockercfg
filename:environment
filename:express.conf
filename:express.conf path:.openshift
filename:filezilla.xml
filename:filezilla.xml Pass
filename:git-credentials
filename:gitconfig
filename:global
filename:history
filename:htpasswd
filename:hub oauth_token
filename:id_dsa
filename:id_rsa
filename:id_rsa or filename:id_dsa
filename:idea14.key
filename:known_hosts
filename:logins.json
filename:makefile
filename:master.key path:config
filename:netrc
filename:npmrc
filename:pass
filename:passwd path:etc
filename:pgpass
filename:prod.exs
filename:prod.exs NOT prod.secret.exs
filename:prod.secret.exs
filename:proftpdpasswd
filename:recentservers.xml
filename:recentservers.xml Pass
filename:robomongo.json
filename:s3cfg
filename:secrets.yml password
filename:server.cfg
filename:server.cfg rcon password
filename:settings
filename:settings.py SECRET_KEY
filename:sftp-config.json
filename:sftp-config.json password
filename:sftp.json path:.vscode
filename:shadow
filename:shadow path:etc
filename:spec
filename:sshd_config
filename:token
filename:tugboat
filename:ventrilo_srv.ini
filename:WebServers.xml
filename:wp-config
filename:wp-config.php
filename:zhrc
HEROKU_API_KEY language:json
HEROKU_API_KEY language:shell
HOMEBREW_GITHUB_API_TOKEN language:shell
jsforce extension:js conn.login
language:yaml -filename:travis
msg nickserv identify filename:config
org:Target "AWS_ACCESS_KEY_ID"
org:Target "list_aws_accounts"
org:Target "aws_access_key"
org:Target "aws_secret_key"
org:Target "bucket_name"
org:Target "S3_ACCESS_KEY_ID"
org:Target "S3_BUCKET"
org:Target "S3_ENDPOINT"
org:Target "S3_SECRET_ACCESS_KEY"
password
path:sites databases password
private -language:java
PT_TOKEN language:bash
redis_password
root_password
secret_access_key
SECRET_KEY_BASE=
shodan_api_key language:python
WORDPRESS_DB_PASSWORD=
xoxp OR xoxb OR xoxa
s3.yml
.exs
beanstalkd.yml
deploy.rake
.sls
— — — — — -BASH — — — — — — — — — —
language:bash password
language:bash pwd
language:bash ftp
language:bash dotfiles
language:bash JDBC
language:bash key-keys
language:bash send_key-keys
language:bash send,key-keys
language:bash token
language:bash user
language:bash login-singin
language:bash passkey-passkeys
language:bash pass
language:bash secret
language:bash credentials
language:bash config
language:bash security_credentials
language:bash connectionstring
language:bash ssh2_auth_password
— — — — — — — — — — — — — — — — — — -PYTHON — — — — — — — — —
language:python password
language:python pwd
language:python ftp
language:python dotfiles
language:python JDBC
language:python key-keys
language:python send_key-keys
language:python send,key-keys
language:python token
language:python user
language:python login-singin
language:python passkey-passkeys
language:python pass
language:python secret
language:python credentials
language:python config
language:python security_credentials
language:python connectionstring
language:python ssh2_auth_password

org:facebookresearch https://
org:facebookresearch http://
org:facebookresearch ldap
org:facebookresearch ftp
org:facebookresearch sftp
org:facebookresearch host:
org:facebookresearch login
```
[Live Tool](https://mr-koanti.github.io/github)
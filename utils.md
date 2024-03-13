-   for copying from gcloud to local machine

```bash
gcloud compute scp --zone "us-west1-a" --recurse cloud-instance-1:~/engagements/* .
gcloud compute scp --recurse cloud-instance-1:~/engagements/loom.com .
gcloud compute scp --zone "us-central1-f" --recurse cloud-instance-1:~/engagements/* .
aputime.com
```

-   logging into cloud

```bash
gcloud compute ssh  "cloud-instance-1" --project "security-assessment-project" --zone "us-central1-f"
```

-   copying file from local machine to remote instance

```bash
gcloud compute scp LOCAL_FILE_PATH VM_NAME:REMOTE_DIR

gcloud compute scp LOCAL_FILE_PATH cloud-instance-1:REMOTE_DIR
```

-   make names in txt file appear on one line

```bash
sed ':a;N;$!ba;s/\n/ /g' wdlist.txt > output_file.txt
```

-   extracting the "Did you mean.." part from graphql field suggestion

```bash
cat response | jq | grep -io 'Did you mean.*'|  sed 's/Did you mean//' | grep -o '[[:alnum:]]\+' |deduplicate
```

Fuzzing.

scanning multiple targets with ffuf

```bash
ffuf -w targets.txt:TARGET -w wordlist.txt -u https://TARGET/FUZZ

nohup stdbuf -oL your_command > output.log 2>&1 &

feroxbuster -u http://127.0.0.1:80/ -w /opt/wordlists/compiled_raft_directories.txt
```

dns brutefrocing can help find other multiple level domains

```bash
# puredns dns bruteforcing

puredns bruteforce wordlist.txt example.com -r resolvers.txt -w output.txt

nohup puredns bruteforce /opt/wordlist/best-dns-wordlist.txt $DOMAIN -r /opt/wordlist/resolvers.txt -w subrute.txt --write-wildcards wildcards.txt --write-massdns from_massdns.txt > sbr2 &

nohup puredns bruteforce ~/wordlist/best-dns-wordlist.txt $DOMAIN -r ~/wordlist/resolvers.txt -w subrute.txt > sbr &

nohup puredns bruteforce ~/wordlist/best-dns-wordlist.txt loom.com -r ~/wordlist/resolvers.txt -w subrute3.txt > sbr3 &

# new and improved puredns bruteforcer.

puredns bruteforce ~/wordlist/best-dns-wordlist.txt $DOMAIN -r ~/wordlist/resolvers.txt -w subrute.txt --write-wildcards wildcards.txt --write-massdns from_massdns.txt

# meant to loop for multilevel domains eg *.app.domain.com
# chnage the output files for this ones
while IFS= read -r DOMAIN; do
    puredns bruteforce ~/wordlist/best-dns-wordlist.txt $DOMAIN -r ~/wordlist/resolvers.txt -w subrute.txt --write-wildcards wildcards.txt --write-massdns from_massdns.txt
done < wildcards.txt

```

-   oneliner for bruteforcing grahql endpoints in found targets

```bash
for i in $(cat live.txt); do echo [$i];graphwoof -d -t $i ; done >> grap2.txt

# onliner.

cat *.txt | sort -u |httpx | anew live.txt && for i in $(cat live.txt); do echo [$i];graphwoof -d -t $i ; done >> grap2.txt

for i in $(cat live_net.txt); do echo [$i];graphwoof -d -t $i ; done >> grap2.txt

```

```bash
clairvoyance https://plexus-prod.skypicker.com/graphql -w /opt/wordlist/30k.txt -0 prodintrospec.json
```

-   IIS server

```bash
nohup shortscan --fullurl https://simulation-learning.telekom.de/ > shrtsc.txt &

for i in $(cat vulniis.txt);do echo [$i]; shortscan --fullurl $i ; done >> shortscn.txt

for i in $(cat vulnIIS.txt);do echo [$i]; shortscan --fullurl $i ; done >> shortscn.txt

```

-   oneliner for extracting js files and endpoints

```bash
for i in $(cat jsfiles|grep main); do echo [$i] ; linkfinder.py -i $i -o cli  ; done  >> endpointsjs

for i in $(cat live.txt); do echo [ + ] $i ; getJS --url $i --complete |anew jsfiles ;done
```

-   top-ports port scan.

```bash
naabu -list basedomain.txt -top-ports 1000 -exclude-ports 80,443,21,22,25 -o ports.txt
# All ports port scan.
naabu -list basedomain.txt -p -  -exclude-ports 80,443,21,22,25 -o ports.txt

```

-   searching urls in archives

```bash
waymore -i domains.txt -mode U --output-urls way/archive.txt
```

kr scan https://formx.cognism.com -w /opt/wordlists/routes-large.kite -x 5 -j 100 --fail-status-codes 400,401,404,403,501,502,426,411

cat wild.txt |xargs -n1 puredns bruteforce ~/wordlist/best-dns-wordlist.txt /opt/wordlist/resolvers.txt -w subrute2.txt

for i in $(cat wild.txt); do puredns bruteforce /opt/wordlist/best-dns-wordlist.txt $i -r /opt/resolvers.txt -w subrute.txt > sbr

-   running ffuf

```bash
ffuf -u example.com -t 5

ffuf -t 5 --w ~/wordlist/raft-large-directories.txt -mc 200,429,405,401,403,204,201 -ic -e .js,.conf,.log,.zip,.bac,.bak,.cache,.save,.tar.gz,.tgz,.templ,.xml,.txt,.tar,.jar,.inc,.ini,.dist,.db,.sql,.aspx,.asp,.rar,.xlsx,.dll,.csv,.xsl,.tmp,.config,.pdf,.doc,.json,.jsp,.conf,.html -o ffuf_output -sf
```

-   jq command for extracting mutations and field names from an introspection response

```bash
jq -r '.data.__schema.queryType.fields[] | .name'

jq -r '.data.__schema.mutationType.fields[] | .name'
```

sed 's/^/get/' data.txt > new_data.txt

```bash
#!/bin/bash

# Read each line from the hosts file
while IFS= read -r line; do
    # Extract the hostname and port from the line
    host=$(echo "$line" | cut -d: -f1)
    port=$(echo "$line" | cut -d: -f2)

    # Generate a filename based on the hostname and port
    filename="${host}_${port}_output.txt"

    # Run nmap command for each host with its port and save the output to a file
    nmap -sV -p "$port" "$host" -oG "$filename"
done < ports.txt

```

```bash
for i in $(cat | targets); do ./subdomain.sh $i ;done

while IFS= read -r line; do

done < foundsites
```

while IFS= read -r DOMAIN ; do
echo $DOMAIN
done < wildcards.txt

-   copying multiple files from server to local machine

````bash
while IFS= read -r DOMAIN ; do
    gcloud compute scp --recurse cloud-instance-1:~/engagements/$DOMAIN .
done < foundsites.txt ```
````

-   extract mutations from introspec urls

```bash
while IFS= read -r DOMAIN ; do
    curl '$DOMAIN' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: altair://-' --data-binary '{"query":"query {\n    __schema {\n        mutationType {\n            fields {\n                name\n            }\n        }\n    }\n}","variables":{}}' --compressed | jq -r '.data.__schema.mutationType.fields[] | .name' | anew mutation_wordlist.txt

done < foundsites.txt

```

-   example curl command to find mutations via introspection

```bash
    curl 'https://cms.harness.io/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: altair://-' --data-binary '{"query":"query {\n    __schema {\n        mutationType {\n            fields {\n                name\n            }\n        }\n    }\n}","variables":{}}' --compressed | jq -r '.data.__schema.mutationType.fields[] | .name' | anew mutation_wordlist.txt
```

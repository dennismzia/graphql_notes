# utilities used when hacking.

-   for copying from gcloud to local machine

```bash
gcloud compute scp --zone "us-west1-a" --recurse cloud-instance-1:~/engagements/* .
gcloud compute scp --recurse cloud-instance-1:~/engagements/cognism/jsfiles .
gcloud compute scp --zone "us-central1-f" --recurse cloud-instance-1:~/engagements/* .
aputime.com
gcloud compute ssh  "cloud-instance-1" --project "security-assessment-project" --zone "us-central1-f"
```

-   copying file from local machine to remote instance

```bash
gcloud compute scp LOCAL_FILE_PATH VM_NAME:REMOTE_DIR

gcloud compute scp LOCAL_FILE_PATH cloud-instance-1:REMOTE_DIR
```

-   Fuzzing.

scanning multiple targets with ffuf

```bash
ffuf -w targets.txt:TARGET -w wordlist.txt -u https://TARGET/FUZZ
```

```bash

nohup stdbuf -oL your_command > output.log 2>&1 &

feroxbuster -u http://127.0.0.1:80/ -w /opt/wordlists/compiled_raft_directories.txt

puredns dns bruteforcing

puredns bruteforce wordlist.txt example.com -r resolvers.txt -w output.txt

nohup puredns bruteforce /opt/wordlist/best-dns-wordlist.txt kevin.eu -r /opt/resolvers.txt -w subrute.txt > sbr &

nohup puredns bruteforce /opt/wordlist/best-dns-wordlist.txt $DOMAIN  -r /opt/resolvers.txt -w subrute.txt > sbr &
nohup puredns bruteforce /opt/wordlist/best-dns-wordlist.txt cognism.com  -r /opt/resolvers.txt -w subrute.txt > sbr &

nohup puredns bruteforce ~/wordlist/best-dns-wordlist.txt $DOMAIN -r ~/wordlist/resolvers.txt -w subrute.txt > sbr &
nohup puredns bruteforce ~/wordlist/best-dns-wordlist.txt tma.telekom.net -r ~/wordlist/resolvers.txt -w subrute3.txt > sbr3 &

nohup for i in $(cat live_net.txt); do echo [$i];graphwoof -d -t $i ; done >> grap2.txt &

clairvoyance https://plexus-prod.skypicker.com/graphql -w /opt/wordlist/30k.txt -0 prodintrospec.json
```

```bash
# IIS server

nohup shortscan --fullurl https://simulation-learning.telekom.de/ > shrtsc.txt &

# for loops for various functionalitites
for i in $(cat jsfiles|grep main); do echo [$i] ; linkfinder.py -i $i -o cli  ; done  >> endpointsjs

# scanning multiple targets with iis shortname scanner

for i in $(cat live.txt);do echo [$i]; shortscan --isvuln $i ; done >> vulnIIS.txt

for i in $(cat vulnIIS.txt);do echo [$i]; shortscan --fullurl $i ; done >> shortScan_output.txt

for i in $(cat vulniis.txt);do echo [$i]; shortscan --fullurl $i ; done >> shortscn.txt

# getting all javascript files
for i in $(cat live.txt); do echo "[ + ] $i " ; getJS --url $i --complete |anew jsfiles ;done

#top-ports  port scan.
naabu -list basedomain.txt -top-ports 1000 -exclude-ports 80,443,21,22,25 -o ports.txt

# searching urls in archives
waymore -i domains.txt -mode U --output-urls way/archive.txt


#All ports port scan.
naabu -list basedomain.txt -p -  -exclude-ports 80,443,21,22,25 -o ports.txt

kr scan https://formx.cognism.com -w /opt/wordlists/routes-large.kite -x 5 -j 100 --fail-status-codes 400,401,404,403,501,502,426,411

cat wild.txt |xargs -n1 puredns bruteforce ~/wordlist/best-dns-wordlist.txt /opt/wordlist/resolvers.txt -w subrute2.txt

for i in $(cat wild.txt); do puredns bruteforce /opt/wordlist/best-dns-wordlist.txt $i  -r /opt/resolvers.txt -w subrute.txt > sbr


for i in $(cat live_net.txt); do echo [$i];graphwoof -d -t $i ; done >> grap2.txt

```

```bash
# running ffuf
ffuf -u example.com -t 5

ffuf -t 5 --w ~/wordlist/raft-large-directories.txt -mc 200,429,405,401,403,204,201 -ic -e .js,.conf,.log,.zip,.bac,.bak,.cache,.save,.tar.gz,.tgz,.templ,.xml,.txt,.tar,.jar,.inc,.ini,.dist,.db,.sql,.aspx,.asp,.rar,.xlsx,.dll,.csv,.xsl,.tmp,.config,.pdf,.doc,.json,.jsp,.conf,.html -o ffuf_output -sf

# copy
nohup ffuf -t 10 -request req.txt -w ~/wordlist/raft-large-directories.txt -mc 200,429,405,401,403,201 -ic -e .js,.conf,.log,.zip,.bac,.bak,.cache,.save,.tar.gz,.tgz,.templ,.xml,.txt,.tar,.jar,.inc,.ini,.dist,.db,.sql,.aspx,.asp,.rar,.xlsx,.dll,.csv,.xsl,.tmp,.config,.pdf,.doc,.json,.jsp,.conf,.html -o ffuf_output -sf > nho &


nohup ffuf -t 10 -u $DOMAIN -w ~/wordlist/raft-large-directories.txt -mc 200,429,405,401,403,201 -ic -e .js,.conf,.log,.zip,.bac,.bak,.cache,.save,.tar.gz,.tgz,.templ,.xml,.txt,.tar,.jar,.inc,.ini,.dist,.db,.sql,.aspx,.asp,.rar,.xlsx,.dll,.csv,.xsl,.tmp,.config,.pdf,.doc,.json,.jsp,.conf,.html -o ffuf_output -sf > out.log 2>&1 &
```

```bash
#!/bin/bash

output_file="combined_output.txt"

while IFS= read -r line; do
    # Extract the hostname and port from the line
    host=$(echo "$line" | cut -d: -f1)
    port=$(echo "$line" | cut -d: -f2)

    # Run nmap command for each host with its port and append the output to the combined file
    nmap -sV -p "$port" "$host" >> "$output_file"
done < ports.txt

```

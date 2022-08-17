### add-dot-at-end
<img src="https://img.shields.io/badge/language-bash-black">
Add . at the end of each line in files.

```
find in -type f -exec cat {} + | sed 's/$/./' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### add-line-to-shodan-query
<img src="https://img.shields.io/badge/language-bash-black">
Add lines to values of shodan query.

```
find in -type f -exec cat {} + | awk '{ if ($0 != "") print "ssl.cert.subject.cn:\"*."$0"\""}'  | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### append-headers-to-csv
<img src="https://img.shields.io/badge/language-bash-black">
Append headers supplied to csv file without them.

```
(echo "vulnerability_id,tags,description,authors,severity,type,host,ip,match,vuln_name,extracted_results,timestamp" && find in -type f -exec cat {} +) > out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### awk-print-last-column
<img src="https://img.shields.io/badge/language-bash-black">
Prints last column of a files in in folder.

```
find in -type f -exec cat {} +  | awk '{print $(NF)}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### awk-take-first-row
<img src="https://img.shields.io/badge/language-bash-black">
Extract first column from all files in in directory.

```
find in -type f -exec cat {} + | awk -F " " '{print $1}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### awk-take-second-row
<img src="https://img.shields.io/badge/language-bash-black">
Extract second column from all files in in directory.

```
find in -type f -exec cat {} + | awk -F " " '{print $2}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### awk-take-third-row
<img src="https://img.shields.io/badge/language-bash-black">
Extract third column from all files in in directory.

```
find in -type f -exec cat {} + | awk -F " " '{print $3}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### cat-all-in
<img src="https://img.shields.io/badge/language-bash-black">
Cat all files in in directory

```
cat in/*/* | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### cat-from-to-lines
<img src="https://img.shields.io/badge/language-bash-black">
Cat file from line number to line number with sed.

```
sed -n 1,100p in/*/* | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### convert-piped-ip-ports
<img src="https://img.shields.io/badge/language-bash-black">
Converts output with | delimiter to ip:port format.

```
find in -type f -exec cat {} + | awk -F"|" '{print $1":"$2}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### count-lines-in-all-files
<img src="https://img.shields.io/badge/language-bash-black">
Used to quickly count all lines inside of all files in in folder.

```
find in -type f -exec cat {} + | wc -l | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### create-wordlist-from-robots-txt
<img src="https://img.shields.io/badge/language-bash-black">
One-liner for generating wordlists from robots.txt

```
find in/ -mindepth 3 -type f -exec cat {} + | egrep -w "Disallow|Allow: " | awk '{print $2}' | sed 's/^\///' | sed 's/\/$//' | sed '/^[[:space:]]*$/d'| sed 's/\*$//' | sed 's/^\*//' | sed 's/\/$//' | sed -e 's/\*\///g' | sed -e s/\*//g | uniq | tee out/output.txt
```
Contributed by [kljunowsky](milan.jovictrickest.com)

---
### custom-script
<img src="https://img.shields.io/badge/language-bash-black">
Create a custom script

```
# edit this
```
Contributed by [trickest](https://trickest.com)

---
### delete-dot-as-first-char
<img src="https://img.shields.io/badge/language-bash-black">
Delete dot when first character, usefull for parsing subdomains with not valid results.

```
cat in/*/* | sed 's/^\.//' | sort -n | uniq | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### delete-dot-as-last-char
<img src="https://img.shields.io/badge/language-bash-black">
Delete dot when it is last character, massdns anyone?

```
cat in/*/* | sed 's/\.$//' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### echo-string
<img src="https://img.shields.io/badge/language-bash-black">
Echo string to output.

```
echo "STRING" | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### egrep-multiple-values
<img src="https://img.shields.io/badge/language-bash-black">
Egrep multiple values and print last in array.

```
cat in/*/* | egrep -w 'url|robots|linkfinder' | awk -F" " '{print $NF}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### egrep-urls-from-list-of-files
<img src="https://img.shields.io/badge/language-bash-black">
Extract urls from list of files with regex.

```
find in -type f -exec cat {} + | egrep -o 'https?://[^ ]+' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### eof-raw-data
<img src="https://img.shields.io/badge/language-bash-black">
Paste raw data and add it to output.

```
cat << "EOF" | tee out/output.txt
ADD_CONTENT_HERE
EOF
```
Contributed by [trickest](https://trickest.com)

---
### extract-ips-with-regex
<img src="https://img.shields.io/badge/language-bash-black">
Extract ip addresses from files with regex.

```
find in -type f -exec cat {} + | grep -E -o "(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)" | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### find-strings-in-meg-responses
<img src="https://img.shields.io/badge/language-bash-black">
Find string in meg responses and print urls.

```
for f in $(find in -mindepth 3 -type f -exec grep 'root:' -R {} + | cut -d":" -f1 | sort -u); do echo "$(head -1 $f) [VULNERABLE]" | egrep '^http'; done | tee out/output.txt
```
Contributed by [gliga](https://trickest.com)

---
### generate-line-batches
<img src="https://img.shields.io/badge/language-bash-black">
Generate batches of lines used for batch-output.

```
BATCH_SIZE=100

find in -type f -exec cat {} + > /tmp/merged.txt FILE_SIZE=$(wc /tmp/merged.txt | awk '{print $1}') for ((i=1;i<=FILE_SIZE;i+=BATCH_SIZE)) do echo $i,$(($i+$BATCH_SIZE)) done | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### generate-random-passwords
<img src="https://img.shields.io/badge/language-bash-black">
Utility to generate random passwords based on pwgen.

```
pwgen -N 100 5 | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### generate-sequence-of-numbers
<img src="https://img.shields.io/badge/language-bash-black">
Sequence of numbers generator!

```
for i in {1..10};do echo $i;done | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### get-asn-prefixes
<img src="https://img.shields.io/badge/language-bash-black">
Get asn prefixes by id.

```
curl --silent https://stat.ripe.net/data/announced-prefixes/data.json\?resource\=ASN_ID | jq -r '.data.prefixes[].prefix' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### get-js-links-from-urls
<img src="https://img.shields.io/badge/language-bash-black">
Get all js links from list of urls

```
find in -type f -exec cat {} +  | grep -Eo "https?://\S+?\.js" | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### gunzip-jsons-to-out
<img src="https://img.shields.io/badge/language-bash-black">
Extract gunzip file and cat json files to out file.

```
gunzip in/*/*.gz && find in -name '*.json' -exec cat {} \;  | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### httpx-json-parse
<img src="https://img.shields.io/badge/language-bash-black">
Parse httpx JSON output to line by line file

```
find in -type f -exec cat {} + | jq -r '"\(try(.url)) \([try(."title")]) \([try(."status-code")]) \([try(."content-length")]) \([try(."content-type")]) \([try(."host")]) \([try(."final-url")]) \([try(."webserver")]) \([try(."technologies")]) \([try(."a"|.[] | tostring)])"' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### jq
<img src="https://img.shields.io/badge/language-bash-black">
JQ for parsing json results.

```
cat in/*/* | jq -r '.results | .[]| "\(.url) \(.status) \(.length) \(.redirectlocation) "' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### mv-regex-files
<img src="https://img.shields.io/badge/language-bash-black">
Move specific files from in to out.

```
mv in/*/*-takeover* out/
```
Contributed by [trickest](https://trickest.com)

---
### parse-nuclei-to-csv
<img src="https://img.shields.io/badge/language-bash-black">
Parse nuclei JSON output to create valid csv

```
find in -type f -exec cat {} + | jq '. | {vulnerability_id: .templateID, tags: .info.tags, description: .info.description, authors: .info.author, severity: .info.severity, type: .type, host: .host, ip: .ip, match: .matched, vuln_name: .matcher_name, extracted_results: .extracted_results|tostring, timestamp: .timestamp}' | jq -r 'to_entries|map(.value)|@csv' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### print-to-lower
<img src="https://img.shields.io/badge/language-bash-black">
Print file content to lowecase

```
cat in/*/* | awk '{print tolower($0)}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### recursively-cat-all
<img src="https://img.shields.io/badge/language-bash-black">
Recursively cat all files in a folder.

```
find in -type f -exec cat {} + | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### recursively-cat-with-extension
<img src="https://img.shields.io/badge/language-bash-black">
Cat all files with custom extension

```
find in -name '*.txt' -exec cat {} \;  | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### remove-whitespaces
<img src="https://img.shields.io/badge/language-bash-black">
Remove whitespaces to files when appending values at the end of lines.

```
find in -type f -exec cat {} + | tr  -d '[:blank:]' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### replace-char-with-new-line
<img src="https://img.shields.io/badge/language-bash-black">
Replaces character with new lines, sorts and deduplicates.

```
find in -type f -exec cat {} + | tr . '\n' | sort -n | uniq | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### replace-dots-with-dash
<img src="https://img.shields.io/badge/language-bash-black">
Replacing dot in strings with dashes

```
cat in/*/* | sed s/[.]/-/g | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### rsync-in-out
<img src="https://img.shields.io/badge/language-bash-black">
Copy all files from in folders to out folder recursively.

```
rsync -rtv in out
```
Contributed by [trickest](https://trickest.com)

---
### script-from-scratch
<img src="https://img.shields.io/badge/language-bash-black">
Create script from scratch.

```
<type-here>
```
Contributed by [trickest](https://trickest.com)

---
### sed-add-at-beginning
<img src="https://img.shields.io/badge/language-bash-black">
Add string at the beginning of each line using sed.

```
find in -type f -exec cat {} + | sed 's/^/https:\/\//' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### sed-add-at-end
<img src="https://img.shields.io/badge/language-bash-black">
Add string at the end of each line using sed.

```
find in -type f -exec cat {} + | sed 's/$/\/FUZZ/' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### sed-replace-words-in-file
<img src="https://img.shields.io/badge/language-bash-black">
Replace "foo" "bar" with words you want to replace in in folder.

```
sed 's/foo/bar/g' in/* | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### sort-uniq
<img src="https://img.shields.io/badge/language-bash-black">
Sort all data and delete duplicates in files in in directory.

```
find in -type f -exec cat {} +  | sort -n | uniq | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### sort
<img src="https://img.shields.io/badge/language-bash-black">
Sort all data in files in in directory.

```
find in -type f -exec cat {} + | sort | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### ungrep-multiple-values
<img src="https://img.shields.io/badge/language-bash-black">
Ungrep multiple strings.

```
cat in/*/* | egrep -wv 'url|robots|linkfinder' | awk -F" " '{print $NF}' | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### unzip-to-out
<img src="https://img.shields.io/badge/language-bash-black">
Unzip files in in folder to out folder

```
unzip in/*/*.zip -d out
```
Contributed by [trickest](https://trickest.com)

---
### wget-list-to-out
<img src="https://img.shields.io/badge/language-bash-black">
Wget list of urls and output to out directory

```
wget -i in/*/* --directory-prefix out
```
Contributed by [trickest](https://trickest.com)

---
### whois-get-registrant-organization
<img src="https://img.shields.io/badge/language-bash-black">
Get registrant organization using whois for domain list file input.

```
for domain in `cat in/*/*`;do;organization=$(whois $domain | grep "Organization");echo $domain $organization;done
```
Contributed by [trickest](https://trickest.com)

---
### wildcard-domains-from-burp-scope-file
<img src="https://img.shields.io/badge/language-bash-black">
Get all wildcard domains from Burp scope json file.

```
find in -type f -exec cat {} + | jq '.target.scope.include[] | .host' | grep "*" | sed 's/\\//g' | sed 's/\"^.\*//g' | sed 's/$\"//g' | sed 's/^\.//'  | sort -n | uniq | tee out/output.txt
```
Contributed by [trickest](https://trickest.com)

---
### zip-to-out
<img src="https://img.shields.io/badge/language-bash-black">
Zip all files and move to out directory

```
zip -r output.zip in && mv output.zip out
```
Contributed by [trickest](https://trickest.com)

---

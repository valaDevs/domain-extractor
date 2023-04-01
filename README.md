# domain-extractor
a simple bash for extracting domains and subdomains from JSON files

## you shoud name the file as `file.json` and pass it to the code

```bash
#!/bin/bash

# Parse JSON file with jq and extract URLs
urls=$(jq -r '.. | strings | select(startswith("http"))' file.json)

# Extract domains and subdomains with grep and sort them
domains=$(echo "$urls" | grep -Eo "(http|https)://[^/]+/" | sort -u)

# Output the result
echo "$domains"
```
## save the file as `domain-extactor.sh` and paste code inside of it

```bash
./domain-extractor.sh file.json
```
or

```bash
bash domain-extractor.sh
```

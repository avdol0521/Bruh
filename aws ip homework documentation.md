making this to keep track of how i did things for future reference
- did an ip search of the site given to me and got its ip. then did a reverse dns search to get all the sites hosted on its server. made a site wordlist 
- did an nmap scan of the wordlist. 
	- command: `nmap -sV -vv -iL allSites.txt -T4 -oN initNMAPoutput.txt`
- seperated the nmap output for individual sites:
```
import re

# Open the Nmap output file
with open('initNMAPoutput.txt', 'r') as file:
    content = file.read()

# Find all the domain sections in the content
domain_blocks = re.findall(r"(Nmap scan report for .+?)(?=\nNmap scan report for |\Z)", content, re.DOTALL)

# Loop through each block and write it to a separate file
for block in domain_blocks:
    # Extract the domain name
    match = re.search(r"Nmap scan report for (.+)", block)
    if match:
        domain = match.group(1).strip()
        # Replace characters that might be invalid in file names
        safe_domain = re.sub(r'[\\/:"*?<>|]', '_', domain)
        with open(f"{safe_domain}.txt", 'w') as domain_file:
            domain_file.write(block)

print("Files created successfully!")
```
- extracted all urls using katana. 
- exracted parameters using a python script
```
def extract_urls_with_equal_sign(input_file, output_file=None):
    """
    Extract URLs containing an equal sign from a text file.
    
    Args:
    input_file (str): Path to the input text file with URLs
    output_file (str, optional): Path to save the extracted URLs. 
                                 If None, prints URLs to console.
    
    Returns:
    list: URLs containing an equal sign
    """
    # List to store URLs with equal sign
    urls_with_equal = []
    
    # Read the input file
    try:
        with open(input_file, 'r', encoding='utf-8') as file:
            for line in file:
                # Strip whitespace and check if URL contains '='
                url = line.strip()
                if '=' in url:
                    urls_with_equal.append(url)
    
    except FileNotFoundError:
        print(f"Error: File '{input_file}' not found.")
        return []
    except IOError:
        print(f"Error: Could not read file '{input_file}'.")
        return []
    
    # If output file is specified, write URLs to it
    if output_file:
        try:
            with open(output_file, 'w', encoding='utf-8') as out_file:
                for url in urls_with_equal:
                    out_file.write(url + '\n')
            print(f"Extracted {len(urls_with_equal)} URLs to '{output_file}'")
        except IOError:
            print(f"Error: Could not write to output file '{output_file}'.")
    
    # If no output file, print URLs to console
    else:
        for url in urls_with_equal:
            print(url)
    
    return urls_with_equal

# Example usage
if __name__ == '__main__':
    # Replace 'input.txt' with your input file path
    # Optionally specify an output file as the second argument
    extract_urls_with_equal_sign('input.txt', 'output.txt')
```
- decided to reduce the fucking scope again. used a bash script to check which sites use wordpress and php 
```
#!/bin/bash

input_file="sites.txt"   # Your list of 400 sites
output_file_php="php_sites.txt"
output_file_wp="wordpress_sites.txt"

# Clear output files
> $output_file_php
> $output_file_wp

while read -r site; do
    echo "Checking $site..."

    # Add http/https if missing
    url=$(echo "$site" | grep -Eo "^(http|https)://.*" || echo "http://$site")

    # Check for WordPress
    if curl -sL "$url/wp-content" | grep -q "403 Forbidden\|404"; then
        echo "$site uses WordPress" | tee -a $output_file_wp
    fi

    # Check for PHP
    if curl -I -s "$url" | grep -qi "X-Powered-By: PHP"; then
        echo "$site uses PHP" | tee -a $output_file_php
    fi

done < "$input_file"

echo "Scan completed!"
```
### other links:
- [[aws ip homework chapgpt response full log]] 
- [[URL extractor python script]] 
- [[nmap list output splicer python script]] 
- [[php and wordpress checker bash script]] 
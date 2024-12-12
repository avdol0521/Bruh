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

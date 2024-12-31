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
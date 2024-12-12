## script:
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
## modification guidelines:

### what to modify:
##### The key parts you might want to change are
1. The filtering condition inside the function
2. The input and output processing

##### For example, if you wanted to filter lines:
- Containing a specific word: `if 'keyword' in line:`
- Starting with a certain prefix: `if line.startswith('http'):`
- Matching a specific pattern: `if re.search(pattern, line):`
- Lines longer than a certain length: `if len(line) > 100:`
- Lines containing numbers: `if any(char.isdigit() for char in line):`
### where to modify:
```
# This is the key line to change
if '=' in url:  # Replace this condition with whatever you want to filter by
    urls_with_equal.append(url)
```
You can replace `'=' in url` with any condition that returns `True` or `False`. For example:

- `line.startswith('http')` to filter URLs starting with 'http'
- `len(line) > 10` to filter lines longer than 10 characters
- `'keyword' in line` to filter lines containing a specific word

The beauty is in its simplicity - just swap out that condition, and you've got a flexible list filter.
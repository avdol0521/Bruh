fuck windows defender man 

- [[GET based LFI]]
- [[POST based LFI]]
- [[RCE]] 
# shit to look out for:
- file inclusion
- those headers
## detection: 
- do proc/self/environ and check for root. if theres root there can possibly be RCE 

## headers to look out for(RCE):
- User-Agent (always check if it prints)
- Accept-Encoding
- Accept 
- Accept-Language
## waf bypass:
<iframe width="600" height="300" src="https://www.youtube.com/embed/fobeXDPJZdk" title="LFI (not acceptable bypass)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

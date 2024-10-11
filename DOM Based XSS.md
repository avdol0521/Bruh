# basic idea:
<iframe width="600" height="300" src="https://www.youtube.com/embed/Rf9OKtbYkeo" title="XSS - What is a &#39;Sink&#39; in Cross Site Scripting?" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
# things to test for:
- [[html sink]] with something like `location.search`
- [[JS execution sink]]
- [[third party dependency sink]]
# things to keep in mind:
- if the data/payload gets URL encoded it probably wont work
- 
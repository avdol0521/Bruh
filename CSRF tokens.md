# testing CSRF tokens:
- remove the token and see if that works
- change the request method from POST to GET 
- see if the token is tied to the user session. if not then any csrf token will work since it doesnt check which user the token originates from 
# testing CSRF tokens and CSRF cookies: 

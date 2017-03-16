# Assumptions

- The technology stack we have allows us to set up a API.
- URL shortener system works as a REST API.
- The shortener API should work at the same host: `http://trav.ix/api/url-shortener`
- URL shortener API doesn't need authentication.
- We have a database to store the shortened urls.
- We don't need to implement a user-interface in the first step, which means in order to shorten a url we have to make a http call.
- Since we have a "variable time to live" we would have different shortened URLs for the same link requested by different users.  

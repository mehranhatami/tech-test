# Questions

- Do we need to setup SSL certificate for trav.ix or it should only work at `http://trav.ix`
- If the answer to the previous question is: "Yes, we need SSL", then:
    - Are we going to host shorthened urls at both `http://trav.ix` and `https://trav.ix` urls?
- Should users be able specify a preferred short url so that we use that instead of generating a random string, so user could have a link like: `http://trav.ix/myawesomepost`
- Other than the "variable time to live" should users be able to remove a shortened url?
- For the API which is in charge of creating new shortened urls, should we allow users to update an already shortened url? Updating an existing shortened url could have different parts to update:
    - To be able to modify the "variable time to live"
    - To be able to change the http method from GET to POST or vise versa.
- The previous question could be also brought up from different angle:
    - Do we have to setup a RESTfull API for shortened urls and support all the methods like GET, POST, PUT, DELETE.
- For "non standard headers" should users be able to specify the list of valid "non standard headers", or we should be able to proxy every single header?
- Do we need some sort of Admin Panel to manage the list of all shortened urls? The answer to this question directly impacts the API definition.
- Are we going to have a technology stack based on a NOSQL database like mongodb or a relational SQL server like MS SQL or MySQL?

# Solution.md

We are going to setup a http server to host all of our endpoints
   - The API which is in charge of our creating new shortened urls: `trav.ix/api/v1/url-shortener`
   - The other one is the one which is going to host the shortened urls at `trav.ix`

We will have a database collection which should store the shortened urls. the data model for this collection would be as below:

```
Url
- shortUrl
- url
- timeToLive
```

## Url Shortener API:

This API supports both GET and POST methods at: `/api/v1/url-shortener` which allows users to send the url as a query-string parameter or a json payload:

    - GET `/api/v1/url-shortener?url=http://stackoverflow.com/questions/tagged/javascript&timeToLive=12`
    - POST `/api/v1/url-shortener` payload:
```
{
  "url": "http://stackoverflow.com/questions/tagged/javascript",
  "timeToLive": 12
}
```

Once the API receives the request it should generate a short url using a specific number of characters like below:
```
"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
```

`timeToLive` is an integer which is the number of hours after which the url shouldn’t be available.
all the 3 values: url, shortUrl, timeToLive are going to be stored in database.

## Short Url proxy
This API is in charge of redirecting to the main url. All we had to do is to receive the request check if the path exists in database and if it exists proxy all the standard and non standard http headers and the possible payload (if it is a POST request) to the main url.

## Time to live
Running a daemon service in background we could filter and simply remove or disable all the urls in the database which they don't have any time left to live.

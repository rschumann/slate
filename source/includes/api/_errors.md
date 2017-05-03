# Errors

<aside class="success">
Remember — the response is jsonapi format
</aside>

Error Code | Meaning
---------- | -------
400 | Bad Request
401 | Unauthorized -- Your API key or authorization is wrong
403 | Forbidden -- The permissions of resource is restricted (AccessDenied)
404 | Not Found -- The specified entity could not be found
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

> Example response:

```json
{
  "errors": [
    {
      "status": "401",
      "title": "Unauthorized"
    }
  ]
}
```

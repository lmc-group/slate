# Errors
The API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The request is hidden for administrators only.
404 | Not Found -- Could not be found.
429 | Too Many Requests -- You're requesting too many concurrences! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
530-539 | Special -- Please see the described message in the response
---
title: Limits
description: How API rate limits works and how to check them.
---
If this is your first time using Scrapebet, you should definitely **know how to check your current rate limits.**

When you choose a pricing plan you will be allowed to make a certain number of request per month. This number will be sent in the `X-Rate-Limit-Limit` field.

You will also be able to find out the rate limits without making additional requests. Each time you call an endpoint, the API will return you within the return headers the following information:

| Header              | Meaning                                      |
| ------------------- | -------------------------------------------- |
| X-Rate-Limit-Limit | Maximum number of requests allowed. This value usually reflects the allowed requests per day. |
| X-Rate-Limit-Reset        | Seconds until the next rate limit.           |
| X-Rate-Limit-Remaining    | Remaining requests allowed.                  |

{%hint info%}
Use the rate limits headers to find out with which frequency you need to make requests.
{%endhint%}

The rate limits are resetted once per day, at 00:00 UTC. If you need to check when is the next reset, be sure to check the `X-Rate-Limit-Reset` value.

### What happens when I exceed my limits?
In case your limits are exceeded, a `429` HTTP error code will be thrown among the error `API_LIMIT_EXCEEDED`.

{%hint warning%}
The rate limit headers still being sent even if an error occurs.
{%endhint%}

```json
{
    "success": false,
    "error": {
        "code": "API_LIMIT_EXCEEDED",
        "message": "You have currently used all your available API requests. Your rate will be available again in 12812 seconds.",
        "http_code": 429,
        "check": "https://docs.scrapebet.com/references/limits"
    }
}
```

You can check the meaning of all [HTTP error codes here](http-error-codes.md) and how they affect to your current rate.

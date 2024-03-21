---
title: HTTP error codes
description: Meaning of all possible HTTP error codes.
---
If you are experiencing an unexpected behaviour in an API response, as part of the answer the server API will return you an error specification and an HTTP response code.

{%hint warning%}To avoid `301` redirects don't use an ending slash `/` in your requests!{%endhint%}

| HTTP code | Meaning                                                                                                                    |
| --------- | -------------------------------------------------------------------------------------------------------------------------- |
| `200`     | Everything seems ok!                                                                                                       |
| `301`     | The endpoint has changed or you are using an slash at the end of the URL.                                                  |
| `400`     | Some request headers or parameters are not valid and the request can't be executed.                                        |
| `401`     | Your API key seems to be correct but you may **not have the sufficient permissions** to access the requested resource.     |
| `403`     | Your API key **is not set or is incorrect**.                                                                               |
| `404`     | The 404 error code happens when a resource you're looking for is not found or just endpoint doesn't exists.                |
| `422`     | Unprocessable entity. You will found more information in the error `message` returned in the response.                     |
| `429`     | You have **exceeded** your allowed API [limits](limits.md).                                                                |
| `500`     | **An unexpected error occurred in our side.** If this is your case please e-mail us and we will check as soon as possible. |
| `503`     | Maintenance period. You can still making request until it's available.                                                     |

### How errors affect to API limits?

You remaining reset **will never be modified when an error occurs.**


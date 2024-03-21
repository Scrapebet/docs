---
title: Authentication
description: Learn how to authenticate and access Scrapebet.
---
### Create your token

Before doing your first request, you will need to **get or create an API token.** You can do this easily accessing to [our website](https://scrapebet.com).

### Adding your API key

In order to make any request, you will need to attach **to every call** the following request header including your token of course!

If the token format is not valid a `400` HTTP code will be sent. In any other case a `403` HTTP code response will be returned.

| Header      | Value       |
| ----------- | ----------- |
| X-Token-Key | Your token. |

{%hint danger%}
Don't share your token publicly! You **must** keep it on your server side.
{%endhint%}

### Authentication error codes

| Error code               | Meaning                                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| `TOKEN_NOT_SET`          | X-Token-Key header was not set.                                                                                                         |
| `TOKEN_FORMAT_INCORRECT` | <p>The authentication header was set but the value format is not valid.</p><p></p><p>It should be a 32-length alphanumeric string. </p> |
| `TOKEN_NOT_VALID`        | If the token format is valid but we can't still authenticate it may not be vinculated with any account.                                 |


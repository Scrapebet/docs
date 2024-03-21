---
title: Response structure
description: How the responses to your calls are structured.
---
Every single request will return some additional information and of course, your result.

### Response fields you will find

You are always returned an array with the following fields:

| Field     | Contents                                                                                                                                                                           |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `success` | Boolean indicating if the request was success (`true`) or not (`false`).                                                                                                           |
| `request` | <p>Information about your request. Only if the request was success. </p><p></p><p>Check "Debug information" below.</a></p> |
| `error`   | <p>Only returned if request failed. </p><p></p><p>Check "Failed requests" below.</p>                                     |
| `result`  | JSON object containing your response if it was success. If request failed this field wont appear.                                                                                  |

### Success requests

Any success request will return a field called `result` which contains the JSON object with your response.

To know the meaning of each of this fields, refer to the endpoint's page where you will find more information about.

{%hint info%}
A valid call can return a `null` in the `result` field if there's no data.&#x20;

Note that a `null` result doesn't necessarily means it has failed as the `result` field only appears when request was correct.
{%endhint%}

### Failed requests

Something has happened! But don't worry yet. In the `error` field you know what's happening here:

| Field       | Contents                                                                                                        |
| ----------- | --------------------------------------------------------------------------------------------------------------- |
| `code`      | Error code. Refer to the endpoint's page to know each meaning.                                                  |
| `message`   | Error message containing more information about it.                                                             |
| `http_code` | <p>Result HTTP code.</p><p></p><p>Check: <a data-mention href="/references/http-error-codes">HTTP Error Codes</a></p> |
| `check` | Optional field, includes the documentation URL that you should check to fix this error. |

### Debug information

Among the `request` field:

| Field         | Contents                                                                          |
| ------------- | --------------------------------------------------------------------------------- |
| `timezone`    | Your current timezone: [Timezones and Dates](/references/timezones-and-dates "mention") |
| `odds_format` | The current odds format: [Odds Formatting](/odds/formatting "mention")  |
| `language`    | Your language: [Languages](/references/languages "mention")                             |
| `answer_time` | The time server took to answer in seconds.                                        |
| `request_id`  | **Unique** identifier for you request. Include this field if you need further support for any endpoint. |

Note that the unique identifier of the request, `request_id`, is also sent within the HTTP headers as `X-Request-Id`. This field won't show if an error occurs.

### JSON pretty printing

Use `?pretty=1` in your URL query parameters to make the response more human readable. The only allowed values are `1` or `0`.

{%hint warning%}
In a production environment, don't use `?pretty=1` **to save bandwidth and make your requests faster.**
{%endhint%}

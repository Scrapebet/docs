---
title: Timezones and dates
description: Set your own timezone for the API requests.
---
When using Scrapebet, all the dates including:

* Event dates.
* Odd update times.
* Bookmaker update times.

Will be returned by the API in [ISO 8601](https://es.wikipedia.org/wiki/ISO\_8601) format using UTC by default.

{%hint warning%}
We strongly recommend you to keep the timezone in UTC as default and change them on your side on a later step.
{%endhint%}

### Changing your timezone

In any other case, you are absolutely free to change based in your needs. In order to do so, use the following header in your requests:

| Header                | Value                |
| --------------------- | -------------------- |
| X-Timezone-Identifier | Timezone identifier. |

{%hint success%}
For example, to request all dates in Spain's timezone use the following header:

**X-Timezone-Identifier: Europe/Madrid**
{%endhint%}

### Get all allowed timezones

All available timezone identifiers can be found in [this list](https://en.wikipedia.org/wiki/List\_of\_tz\_database\_time\_zones). The value "TZ database name" is the one you will need.

We have an endpoint to check all our available timezones:

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3>[link] https://api.scrapebet.com/v1/timezones</h3>
    <div class="desc lead">Retrieve all allowed timezones.</div>
  </div>
</div>

### Timezones error codes

| Error code                  | Meaning                                                                            |
| --------------------------- | ---------------------------------------------------------------------------------- |
| `TIMEZONE_NOT_VALID`        | Although the format is correct, the time zone used is not available in our system. |
| `TIMEZONE_FORMAT_INCORRECT` | The used format is not correct.                                                    |




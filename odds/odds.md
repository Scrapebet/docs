---
title: Odds
description: All available odds and prices for each bookmaker in an event. 
---
The odds endpoint allows provides you a unified result with the most updated and available odds from each bookmaker in all markets. You **must provide an event ID** to download the odds.

### Odds structure
The result of this endpoint will include different nested objects with different deeps. Take a few minutes to see how data is structured in this endpoint:
<img src="/assets/odds.png" loading="lazy" style="margin:30px auto;">

### Deep levels
* **1st level:** Includes market and name available in the event.
* **2nd level:** Includes the odd name, like `Real Madrid`, `Barcelona` fpr `Winner` or `No` for `Both teams to score`. This level also includes the `line` if required and other useful data.
* **3rd level:** This level is nested within the `bookmakers` object. Includes all available bookmakers for this odd.
* **4th level:** The current price for the bookmaker, the first price ever, last update and creation date.
* **5th level:** The odd's price evolution during time if requested with `&historical=1` in the query parameters.

### Endpoint
<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg> https://api.scrapebet.com/api/v1/odds?event_id=[id]</h3>
    <div class="desc lead">Retrieve available markets with a sport ID.</div>

<details>
<summary>Example of a response</summary>

```json

"result": [
    {
      "market_id": "43f397fd304e004eec7b672d",
      "market": "Half Time/Full Time",
      "odds": [
        {
          "short_name": "X/2",
          "name": "Draw/Olympiacos",
          "bookmakers": [
            {
              "odd_id": "665d79b584879ebe7caa1ab6",
              "bookmaker_id": "bet365",
              "created": "2024-06-03T08:07:15+00:00",
              "last_update": "2024-06-04T09:15:59+00:00",
              "first": 36,
              "now": 34
            }
          ]
        }
      ]
    }
  ]

```
</details>

  </div>
</div>

### 1st level fields
The odds endpoint returns an array of [markets](/odds/markets). Each market includes a 'odds' array.

| Field | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `market_id`       | `id` of the market. All markets can be retrieved with the [markets](/odds/markets) endpoint.                                                                                                                              |
| `market`          | The market name in the language you requested. Check [how to change the language here](/references/languages)     |
| `odds`      | A nested object with all available odds. Check the following level. |

Each 'odds' contains an array of odds. For example, if you're requesting the odds for 1X2 market, this array would include

### 2nd level fields
| Field | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `short_name`       | `1`, `X`, `2`... |
| `name`          | `Real Madrid`, `No penalty awarded`, `5 or more corners`... Check [how to change the language here](/references/languages)     |
| `bookmakers`      | A nested object with all available bookmakers. Check below for more information about. |

### 3rd and 4th level fields
| Field | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `odd_id`       | Unique identifier for the odd & bookmaker in this event and market. |
| `bookmaker_id` | Bookmaker identifier.  |
| `created`      | Timestamp with the date this odd was added to the API. Refer to [Timezones and dates](/references/timezones-and-dates) to know more about the date formats. |
| `last_update`      | Last update timestamp. Refer to [Timezones and dates](/references/timezones-and-dates) to know more about the date formats. |
| `first`      | Price when the odd was added. Refer to [formatting](/odds/formatting) to change between decimal and other formats. |
| `now`      | Most recent price. Refer to [formatting](/odds/formatting) to change between decimal and other formats. |
| `historical`      | Odd prices evolution for this bookmaker. Only shown if `&historical=1` is in the query parameter. |

### 5th level fields
| Field | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `odd`       | Price for the `date`. |
| `date` | Date timestamp when this odd was modified.  |

{%hint warning%}Notice that in the historical fields the `now` and `first` values are never included.{%endhint%}

You can see <a href="/assets/examples/odds_endpoint.json" target="_blank" rel="nofollow noopener">an example response here</a>. This is a request for a soccer event filtered with one bookmaker, winner market, language set to Spanish and historical odds evolution.

### Filtering
You can use filters to choose which [bookmakers](/odds/bookmakers) and [markets](/odds/markets) are returned. Remember that you can also filter for a group of bookmakers for a certain country if needed. Check the previous pages for more information.

All filters are set with query parameters.

### Odds error codes
You may encounter during a few common error codes which usually happens when you misspell the ID during the request.

| Error code                 | Meaning                                                                                                                                                                                                     |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ODDS_NOT_FOUND`          | No odds available in the event yet. This error should be uncommon to see. |
| `ODDS_FILTERS_NOT_FOUND`    | In case you're filtering the request, this error will be thrown if a query parameter is empty or wrong. |
| `ODDS_MOVEMENT_NOT_ALLOWED` | You'll see this error if you use `&historical=1` to get a specific odd evolution during time and your account does not have this [scope](/references/scope-and-trial-accounts). |
<br>

If you are returned an error not prefixed with `ODDS_`, you should check the corresponding section. The following ones are the most common:
* [Scope errors](/references/scope-and-trial-accounts)
* [Events errors](/the-basics/events)
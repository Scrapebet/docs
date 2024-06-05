---
title: Bookmakers
description: Get all the available bookmakers, their operation countries and updates timestamps.
---
Before setting up your API workflow, you should know the bookmakers integrated with Scrapebet.&#x20; We use **a single endpoint** for this task which we encourage you to cache in a weekly basis in your app.

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3>[link] https://api.scrapebet.com/v1/bookmakers</h3>
    <div class="desc lead">Retrieves the list of all available bookmakers.</div>

<details>
<summary>Example of a response</summary>

```json
{
  "bookmakers": [
    {
      "id": "5cebb6ef21232f1018004419",
      "running": true,
      "name": {
        "short": "Bet365",
        "long": "Bet365"
      },
      "update": {
        "last": "2019-05-27T10:00:00.000Z",
        "average_time": 300
      },
      "exange": false,
      "has_live_matches": false,
      "available_countries":
      [
        "MX",
        "ES"
      ],
    }
  ]
}
```
</details>

  </div>
</div>

### Checking if a bookmaker is being updated

At some point, our bookmakers may start a maintenance period, or just be unavailable for a short period of time. If this happens, this endpoint is also useful to **know the current status** for each bookmaker with the `running` field.

### Filter bookmakers in the responses
Almost every single endpoints admits bookmakers query parameter, which will allow to filter the allowed bookmakers in the response.

It accepts a single id or a comma-separated list.

``?bookmakers=bet365,888sport,1xbet`` or ``?bookmakers=bet365``.

### Include only a set of bookmakers
Almost every single endpoints admits bookmakers query parameter, which will allow to filter the allowed bookmakers in the response.

It accepts a single id or a comma-separated list.

`?bookmakers=bet365,888sport,1xbet` or `?bookmakers=bet365`

### Get bookmakers only for certain countries
If your web app or target is from a specific country or countries, you can filter them without the ID using the following query parameter:
`?bookmaker_countries=ES,AR,GB`

### Exclude bookmakers
If your web app or target is from a specific country or countries, you can filter them without the ID using the following query parameter:
`?bookmaker_exclude=versus,betway`

### Important fields to notice of

* The **internal bookmaker id**, which you will use later to retrieve information for a specific market.
* **Average update time**, in order to know how much frequency your requests should have.

### Bookmaker operating countries

Countries **where the bookmaker operates and we can provide you**, in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2#Officially\_assigned\_code\_elements) country code. If you run a multi-country odds app, you will ne

### Fields description

| Field       | Meaning                                                                                                                                                                                                                                                                                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`        | The bookie identifier code in Scrapebet. |
| `image`    |  URL for the bookmaker logo. |
| `running`   | <p>A bool that indicates if the bookmaker odds are being updated.</p><p></p><p>If it says <code>false</code> the bookie won't update its own odds until its `true` again. |
| `name`      | An array containing two types of names. A `short` and a `long` name. |
| `update`    | `last` time timestamp this bookmaker was executed and the `average_time` to update all odds. |
| `hex_color` | Main corporative color in hexadecimal format `#FFFFFF` for the bookie. |


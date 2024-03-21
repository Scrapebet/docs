---
title: Sports
description: Get all sports into your app!
---
Almost everything in Scrapebet revolves around a **sport**. All markets, leagues and events are related to sports in first place.

### Get all sports

There are no extra parameters for this call. You get all sports at once. Let's start working out with the Scrapebet API! Make your first call:&#x20;

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3>[link] https://api.scrapebet.com/v1/sports</h3>
    <div class="desc lead">Retrieves a list of all available sports.</div>
  </div>
</div>

### Sport fields

| Field        | Meaning                                                   |
| ------------ | --------------------------------------------------------- |
| `id`         | Sport ID. Use it among your request to filter.            |
| `name`       | Sport name.                                               |
| `events`     | Number of `incoming` and `historical` events.             |
| `leagues`    | Number of leagues attached to this sport.                 |
| `markets`    | Number of available odd markets.                          |
| `bookmakers` | Available bookmakers for the sport and last update times. |

### Caching your request

Sports do not change often so unless you want to check how many events are scheduled it is a good idea to save resources and rate limits caching your request.

{%hint info%}
We recommend to access no more than a few times a month the sports endpoint.
{%endhint%}


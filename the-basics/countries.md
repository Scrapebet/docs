---
title: Countries
description: Find out the available countries to filter leagues, events and teams.
---
In order to get some specific events or leagues you may filter by a country ID if needed. However, you don't need to fetch the countries to work with the API.

{%hint warning%}
Some leagues may be named the same but be attached to different countries.&#x20;

:point\_right: Make sure to use the **correct league ID.**

:point\_right: We suggest to filter your request by the **country ID** if possible.
{%endhint%}

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3>[link] https://api.scrapebet.com/v1/countries</h3>
    <div class="desc lead">Get all countries.</div>
  </div>
</div>

### Country fields

| Field          | Meaning                                                                                                                     |
| -------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `id`           | The country ID.                                                                                                             |
| `name`         | The name of the country.                                                                                                    |
| `country_code` | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2#Officially\_assigned\_code\_elements) country code. |

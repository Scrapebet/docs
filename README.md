---
title: Get started
description: Welcome to Scrapebet!
---
Scrapebet provides a real-time API with sports events, stats and mainly, betting odds.

### Getting your token

The first thing you need to know is how [authentication.md](references/authentication.md "mention") works and generate your first token. This is a mandatory step to access the endpoints.

### Before making your first request

Before making your first call, we highly suggest to make a fast-check in "References".

* [HTTP Error Codes](references/http-error-codes "mention")
* [API Limits](references/limits "mention")
* [Languages](references/languages "mention")

{%hint success%}Don't forget to assign your [Timezone and date](references/timezones-and-dates "mention").{%endhint%}

### Endpoints

Scrapebet works with just a **few simple and unified** endpoints that allows you to filter efficiently all the information you need.

There are more endpoints that you will find in each section, those are the most important and the endpoints you'll frequently use.

#### Avoid common error when calling endpoints

{%hint danger%}
Please do not use any other HTTP method than `GET`.&#x20;

Using methods like `PUT` or `POST` will result in a `404` or `403`. Check [http-error-codes.md](references/http-error-codes.md "mention") for more information.
{%endhint%}

{%hint danger%}
Don't use ending slashes `/` to avoid `301` redirections.
{%endhint%}

#### Sports data endpoints

* [Sports](the-basics/sports)
* [Countries](the-basics/countries)
* [Leagues](the-basics/leagues/)
* [Events](the-basics/events)
* [Teams and players](the-basics/teams-and-players)

#### Odds comparison endpoints

* [Bookmakers](odds/bookmakers)
* [Markets](odds/markets)
* [Odds](odds/odds/)

### Data schema

Just one more thing before you go. This is how data is structured internally in our API. You may find this diagram flow useful to learn how sports, teams, events, countries,... are related to each other.

![How data is structured](/assets/schema.png)

---
title: Markets
description: Retrieve all markets from a sport with the markets endpoint.
---
In order to help you filter on a later stage the results from your calls, make sure to locally save the `market_id` of the markets you're interested in.

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg> https://api.scrapebet.com/api/v1/markets?sport_id=[id]</h3>
    <div class="desc lead">Retrieve available markets with a sport ID.</div>
  </div>
</div>

For example, to fetch all the markets in soccer, use:

`https://api.scrapebet.com/v1/markets?sport_id=`5cebb6ef21232f1018004419\&pretty=1

The answer contains a nested array with the `market_id`, the market `name`, and information about `bookmakers` available and their update times.

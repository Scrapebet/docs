---
title: Leagues
description: Get leagues information with just a Sport ID.
---

To find leagues you will need at first place a **Sport ID** which can be found in the [Sports](../sports "mention") page. This makes it super easy to collect all your content into logical and ordered groups.

Let's start! Make your first request using the following endpoint:

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg> https://api.scrapebet.com/v1/leagues</h3>
    <div class="desc lead">Retrieve leagues information from a sport.</div>
    
| Parameter         | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sport_id`       | Sport ID to pull leagues from.                                                                                                                          |   
| `league_id`       | League ID, in case you need to fetch an specific league.                                                                                                                          |            
| `tables`       | Specify this parameter if you'd like to return tables and standings information.                                                                                                                          |                                                                                                                
  </div>
</div>

### Leagues error codes

| Error code              | Meaning                                                                                                    |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- |
| `SPORT_NOT_FOUND`       | The provided Sport ID couldn't be found.                                                                   |
| `LEAGUES_NOT_AVAILABLE` | There are no available leagues for the Sport ID.                                                           |
| `LEAGUE_NOT_FOUND`      | In case that you provide a League ID, if it's not found within the Sport bounds this error will be thrown. |


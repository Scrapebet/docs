---
title: Teams and players
description: In Scrapebet we distinguish between temas and players. Learn of to difference them.
---

In Scrapebet we distinguish between teams and players. The only effective difference is that players are referred to a single person.

In the teams endpoint **only teams will be returned.**

<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg> https://api.scrapebet.com/v1/teams</h3>
    <div class="desc lead">Retrieve all teams for a sport ID.</div>
    
| Parameter         | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sport_id`       | Sport ID to retrieve teams from.                                                                                                                         |                                                                            
  </div>
</div>

### Teams & players fields

| Field              | Meaning                                                                                                                                                                                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`               | Team ID.                                                                                                                                                                                                                                                    |
| `name`             | Team/player name.|
| `is_player` | Boolean indicating whether the team is a person or not.                                                                                                                                                                                                  |
| `national_team`        | Boolean that indicates if this team is a national team like 'Spain', 'France' or 'United States'. |
| `gender`           | The team or player gender, `male`, `female` or `null` if the gender is not set yet.                                                                                                                                                                        |
| `country`          | The player country in ISO 3166-1 alpha-2 format. In case of teams, corresponds to the country where the team play in. `null` if not available.                                                                                                                                                                          |
| `urls`             | <p>Nested array with useful URLs related to the team or player. </p><p></p><p>At the moment, only available in some teams including the <code>wikipedia</code> URL.</p>                                                                                     |
| `subsidiary_teams` | <p>If the team has any known subsidiary teams, this field will return a nested array with the teams <code>id</code> and <code>name</code>(s).</p><p></p><p>Please note that this field is only informative, <strong>all teams are treated as unique</strong> even if they are listed as subsidiary here.</p> |
| `has_shield`        | Boolean, true or false if this team or player has an image. When it's true, then [you can download the picture](/the-basics/teams-and-players/shields-and-pictures "How to download the team's shields?"). This field does not appear when you're under a trial period. |
| `abbr` | Team abbreviation. |
### Error codes

| Error code            | Meaning                                    |
| --------------------- | ------------------------------------------ |
| `TEAMS_NOT_AVAILABLE` | No teams available for the given Sport ID. |

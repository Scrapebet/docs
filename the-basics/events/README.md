---
title: Events
description: Get information about events.
---

The **fastest and most reliable way to obtain an event** information is filtering with it's own ID. Every single event, even if the teams have played more than once have it's unique ID.


<div class="card endpoint">
  <span class="ribbon"><span>ENDPOINT</span></span>
  <div class="card-body">
    <h3><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg> https://api.scrapebet.com/v1/events</h3>
    <div class="desc lead">Get an event based on it's ID.</div>
    
| Parameter         | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `event_id`       | Unique identifier for the event. |    
| `sport_id`       | Returns events only for one specific sport.                                                                                                                           |   
| `league_id`       | Returns events for the league.                                                                                                                           |            
| `country_id`       | Returns events for the specified country.                                                                                                                          |                 
| `type`  | Choose a type of event. (Check the table below) |
| `limit`  | Number of events to return in a single query, from 1 to 1000. |
| `day`  | Return all the available events for the day, use dd-mm-YYYY format. |
| `from`  | This is the **minimum** event **start** date. (Check date filters below) |
| `to`  | This is the **maximum** event **start** date. (Check date filters below) |
| `onlyWithResults`  | When this query parameter is sent, only ended events with results available will be shown. 'type' must be 'ARCHIVED'. |
  </div>
</div>

{%hint info%}
For returning a single event, use `event_id` and every other parameter will be ignored. No fields are mandatory.
{%endhint%}

### Event fields

| Field         | Meaning                                                                                                                                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sport`       | `id` and `name` of the sport for this event. |
| `id`          | The event ID.                                                                                                                                                                                                                          |
| `league`      | <p>A nested object with the league <code>id</code> and <code>name</code>.</p><p></p><p>In most of cases, it may return a country <code>id</code> and <code>name</code> as well.</p>                                                    |
| `country`     | <p>The league's country <code>id</code> and <code>name</code>, if available.</p><p></p><p>If there is no country attached to the league, this field will be <code>null</code>.</p>                                                     |
| `teams`       | `local` and `away` teams with their respective `id` and `name`.                                                                                                                                                                        |
| `type`        | <p>Type of event: <code>UPCOMING</code>, <code>ARCHIVED</code> or <code>LIVE</code>. </p><p></p><p>If you don't specify the <code>?type=</code> query parameter, by default only <code>UPCOMING</code> will be shown.</p>              |
| `status`      | <p>The current status for the event. </p><p></p><p>It can be: <code>NOT_STARTED</code>, <code>FINISHED</code>, <code>POSTPONED</code>, <code>CANCELLED</code>, <code>IN_PLAY</code>, <code>BREAK_TIME</code>, <code>UNKNOWN</code>.</p> |
| `date`        | The event date. You can know more about the timezone and the format used in [Timezones and dates](/references/timezones-and-dates "mention"). |
| `last_update` | Timestamp when the last update on the event was performed.                                                                                                                                                                             |
| `tv`          | Check: [TV Channels](/the-basics/events/tv-channels "mention") |
| `created`     | Date when the event was added to the API. |
| `ended`       | End time of the event. |
| `week` | Week number, relative to the event's year. |
| `cc`          | Count of total available bookmakers for this event.                                                                                                                                                                                    |
| `winning_chances` | Event results predictions based on our aggregated odds data and historical statistics. Check [Winning chances](/the-basics/events/winning-chances "mention") for a few examples. |
| `bookmakers`  | List of all available bookmakers for this match and their update times.                                                                                                                                                                |

### Date filters
When querying with date filters, you must use UTC. Although date filters requires an UTC input it won't affect your timezone configuration.

Regarding the formats, you can use 'dd/mm/YYYY' in both 'to' and 'from' fields. In this case, the hour will be set as 00:00 (UTC) by default. You can also use an UNIX timestamp (recommended) to indicate hours as well.

### Events error codes

You may encounter during a few common error codes which usually happens when you misspell the ID during the request.

| Error code                 | Meaning                                                                                                                                                                                                     |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `EVENT_NOT_FOUND`          | The event couldn't be found.                                                                                                                                                                                |
| `EVENT_ID_WRONG_FORMAT`    | Error that happens when querying for just one event. Only thrown if the **ID is not valid**.                                                                                                                |
| `EVENT_UNPROCESSABLE`      | <p>Some events can be faulty from time to time depending on the bookmaker that is providing it. </p><p></p><p>If you find this error please make sure to read the error <code>message</code> returned. </p> |
| `EVENT_LEAGUE_UNAVAILABLE` | This error will be thrown if you're trying to access to an event and the league attached to it is not ready for production use.                                                                             |
| `EVENT_UKNOWN_TYPE`        | If you specify a wrong event type in the URL this error will be thrown. |
| `EVENT_NOT_SET`        | May occur in different endpoints when the required `event_id` query parameter is not set. |
| `RESULTS_SCOPE_NOT_ALLOWED` | Will be thrown when querying results specific filters without the scope enabled. |

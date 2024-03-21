---
title: Examples
description: Quick examples to get started for first time.
---
# Sports
## Get all available sports
```https://api.scrapebet.com/v1/sports```

## Get all available sports excluding the name and incoming events count
```https://api.scrapebet.com/v1/sports?exclude=name,incoming_events```

# How do I retrieve the events from a specific league?
## Get available events from Spanish Primera
1. Find the sport ID (Football)
```https://api.scrapebet.com/v1/sports```

2. Fetch the leagues from Football using the ID
```https://api.scrapebet.com/v1/leagues?sport_id=5cebb6ef21232f1018004419```

3. Now you're ready to get the events from Primera. It's a good idea to cache the IDs.
```https://api.scrapebet.com/v1/leagues?sport_id=5cebb6ef21232f1018004419&league_id=2c937341a5a4ede08bf22df5&type=UPCOMING```

# How do I fetch a single event?
With the event ID, for example __6248c49296bc96663f31a7c3__ make the following request:
```https://api.scrapebet.com/v1/events?event_id=6248c49296bc96663f31a7c3```

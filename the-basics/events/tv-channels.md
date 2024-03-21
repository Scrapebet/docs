---
title: TV Channels
description: Where I can see this event? Here you can find out.
---

TV channels are only available in certain events. When calling the [.](./ "mention") endpoint TV channels are returned by default if available.

{%hint info%}
TV channels are returned in a nested array within an event object. If no TV is available for the event, then value for `tv` will be `null`.
{%endhint%}

### TV fields

| Field          | Meaning                                                                                                                          |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `name`         | TV channel name.                                                                                                                 |
| `country_code` | TV's [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2#Officially\_assigned\_code\_elements) country code. |

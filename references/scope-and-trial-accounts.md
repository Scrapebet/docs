---
title: Scope and trial accounts
description: How trial accounts works and regular accounts scope.
---
Each token have a scope assigned. This scope allows you to access a different range of sports, markets, events and leagues.

If you already have determined with your sales agent you won't have a scope limit, you can skip this part of the documentation.

{%hint danger%}
When you hit an endpoint which is not on your scope, an explanatory error message will appear with an error code similar to **[ENDPOINT]_OUT_OF_SCOPE** or **[ENDPOINT]_NOT_ALLOWED**.
{%endhint%}

### Limits in test accounts
When you're under a trial period, your account may be limited in a different way than regular accounts.

**Some of the restrictions could include:**
* Historical odds.
* Archived/historical events.
* TV channels information for a event.
* Teams database.

Some specific endpoints may return a `TRIAL_ACCOUNT_NOT_ALLOWED` error if you're trying to access endpoints where you don't have access to. If you need to access this data, please [contact](https://scrapebet.com/contact) our support.

### Error codes associated with trial periods

| Error code | Meaning |
| -------------------------- |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `TRIAL_ENDED` | Your current trial period has ended. |
| `TRIAL_ACCOUNT_NOT_ALLOWED` | Access to this endpoint or this specific data is not allowed during a trial. |

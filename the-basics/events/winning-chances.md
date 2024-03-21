---
title: Winning chances
description: Winning chances for each team in the event.
---

If available at the moment of the request, each event will return it's prediction among the rest of the response object in a nested array called `winning_chances` in Scrapebet.

{%hint info%}
Predictions are only available in `UPCOMING` events.
{%endhint%}

### How winning chances are calculated

The predictions are actually based in the highest trust source: our odds.&#x20;

First, we collect the highest odds for each team and then we calculate the **implied probability** of the highest odds for each team:

``
f(probability) = (1/odd) * 100
``

Finally, we convert then to real probability. That means that the bookmarker margins are no longer in the probabilities that you are given.

### Fields

| Field  | Meaning                                                                                                                                                                                        |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `home` | Probability percentage of **home team winning.**                                                                                                                                               |
| `draw` | <p>Probability percentage of <strong>event resulting in a tie.</strong></p><p></p><p>If there are no possibilities of draw in the event's sport, the this field will be <code>null</code>.</p> |
| `away` | Probability percentage of **away team winning**.                                                                                                                                               |

{%hint warning%}
Notice that some events may not have a `home` or `away` team at all. This can happens when **both teams play in a third-party stadium for example**.

If this is the case, refer to the event `teams` field to know which one are them.
{%endhint%}

### Example responses

**Football**
```
// Levante - Athletic Bilbao (La Liga Spain - 19/11/2021)

"winning_chances": {
    "home": 31.108597285067873,
    "draw": 29.69457013574661,
    "away": 39.196832579185525
}

/* ... Rest of the event */
```

**Basketball**
```
// Denver Nuggets - Atlanta Hawks (NBA - 13/11/2021)

"winning_chances": {
    "home": 61.15107913669064,
    "away": 38.84892086330936
}

/* ... Rest of the event */
```

**Tennis**
```
// Alexander Zverev - Matteo Berrettini (ATP Finals - 14/11/2021)

"winning_chances": {
    "home": 67.87330316742081,
    "away": 32.12669683257918
}

/* ... Rest of the event */
```

**No predictions available**
```
// Any other event with no information about.

"winning_chances": null

/* ... Rest of the event */
```

{%hint success%}
Please note **that predictions are available in almost are sports**. These are just examples for the most common sports.
{%endhint%}


---
title: Formatting
description: 'Time to choose: Decimal, fractional or moneyline odds.'
---

{%hint info%}
All odds in our comparison API are returned as **decimal odds** by default. If you're ok with this, you won't need to make any further changes.
{%endhint%}

### Changing odds format

All you need to do is add the following header in your request. If the odds format header value is not valid an error will be thrown.&#x20;

| Header        | Value                                                                  |
| ------------- | ---------------------------------------------------------------------- |
| X-Odds-Format | Use one of the [#formats](odds-format.md#formats "mention") available. |

### Formats

{%hint info%}
Note that format types are **case sensitive**.
{%endhint%}

| Type                    | Results example | Field type |
| ----------------------- | --------------- | ---------- |
| `DECIMAL`               | 1.11            | `float`    |
| `FRACTIONAL`            | 1/9             | `string`   |
| `AMERICAN`, `MONEYLINE` | -900            | `integer`  |

### You must know

* Fractional odds **are always reduced** to it's lowest terms.
* American and moneyline formats are the same. You can choose between one of them freely.
* Moneyline odds **are always** preceded by a "+" or a "-".
* **The lowest possible existing odd is 1.01.**
* Decimals odds are truncated to **** 2 places.
* You won't never find a :x:<mark style="color:red;">**2.7**</mark> or a :x:<mark style="color:red;">**1.3**</mark> decimal odd, instead :white\_check\_mark:<mark style="color:green;">**2.70**</mark> or :white\_check\_mark:<mark style="color:green;">**1.30**</mark>.

### Odds format error codes

| Error code              | Meaning                                                         |
| ----------------------- | --------------------------------------------------------------- |
| `ODDS_FORMAT_INCORRECT` | The format is not valid. Choose between one of the types above. |


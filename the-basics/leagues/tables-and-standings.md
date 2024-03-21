---
title: Tables and standings
description: Retrieve information about tables and standings.
---

In order to retrieve tables, the only thing you need to do is call the [Leagues](./ "mention") endpoint and add `&include=tables` to the end of your URL.

{%hint info%}
Remember you can also filter to return only the data for a specific League. Check out the parameters for [Leagues](./ "mention").
{%endhint%}

### Example response

```
{
  "tables": {
    "available": true,
    "last_update": "2021-11-08T18:28:57+00:00",
    "data": [
      {
        "name": "LaLiga",
        "round": "13",
        "max_rounds": "38",
        "rows": [
          {
            "position": {
              "current": "1",
              "change": "0"
            },
            "stats": {
              "win": "8",
              "draw": "4",
              "loss": "1",
              "goals": {
                "for": "19",
                "against": "10"
              },
              "points": "28"
            },
            "team": {
              "id": "5d443a495ff25009f6095513",
              "name": "Real Sociedad"
            }
          },
          {
            "position": {
              "current": "2",
              "change": "0"
            },
            "stats": {
              "win": "8",
              "draw": "3",
              "loss": "1",
              "goals": {
                "for": "28",
                "against": "13"
              },
              "points": "27"
            },
            "team": {
              "id": "5d5197719dc6d6755e6b2dc2",
              "name": "Real Madrid"
            }
          },
          {
            "position": {
              "current": "3",
              "change": "0"
            },
            "stats": {
              "win": "8",
              "draw": "3",
              "loss": "1",
              "goals": {
                "for": "21",
                "against": "7"
              },
              "points": "27"
            },
            "team": {
              "id": "5d443c6d5ff2500c9628b8b2",
              "name": "Sevilla"
            }
          },
          {
            "position": {
              "current": "4",
              "change": "0"
            },
            "stats": {
              "win": "6",
              "draw": "5",
              "loss": "1",
              "goals": {
                "for": "21",
                "against": "13"
              },
              "points": "23"
            },
            "team": {
              "id": "5d443a3d5ff25009f6095512",
              "name": "Atlético Madrid"
            }
          },
          {
            "position": {
              "current": "5",
              "change": "0"
            },
            "stats": {
              "win": "6",
              "draw": "3",
              "loss": "4",
              "goals": {
                "for": "19",
                "against": "17"
              },
              "points": "21"
            },
            "team": {
              "id": "5d443a505ff25009f6095514",
              "name": "Betis"
            }
          },
          {
            "position": {
              "current": "6",
              "change": "0"
            },
            "stats": {
              "win": "6",
              "draw": "2",
              "loss": "5",
              "goals": {
                "for": "19",
                "against": "14"
              },
              "points": "20"
            },
            "team": {
              "id": "5d5198039dc6d6759f4e23eb",
              "name": "Rayo Vallecano"
            }
          },
          {
            "position": {
              "current": "7",
              "change": "0"
            },
            "stats": {
              "win": "5",
              "draw": "4",
              "loss": "4",
              "goals": {
                "for": "14",
                "against": "17"
              },
              "points": "19"
            },
            "team": {
              "id": "5d443ece5ff250100c7d25e4",
              "name": "Osasuna"
            }
          },
          {
            "position": {
              "current": "8",
              "change": "0"
            },
            "stats": {
              "win": "4",
              "draw": "6",
              "loss": "2",
              "goals": {
                "for": "11",
                "against": "8"
              },
              "points": "18"
            },
            "team": {
              "id": "5d443c765ff2500c9628b8b3",
              "name": "Athletic Bilbao"
            }
          },
          {
            "position": {
              "current": "9",
              "change": "0"
            },
            "stats": {
              "win": "4",
              "draw": "5",
              "loss": "3",
              "goals": {
                "for": "19",
                "against": "15"
              },
              "points": "17"
            },
            "team": {
              "id": "5d443e085ff2500f1d52f522",
              "name": "Barcelona"
            }
          },
          {
            "position": {
              "current": "10",
              "change": "0"
            },
            "stats": {
              "win": "4",
              "draw": "5",
              "loss": "4",
              "goals": {
                "for": "21",
                "against": "20"
              },
              "points": "17"
            },
            "team": {
              "id": "5d443dca5ff2500ee03ced82",
              "name": "Valencia"
            }
          },
          {
            "position": {
              "current": "11",
              "change": "0"
            },
            "stats": {
              "win": "4",
              "draw": "5",
              "loss": "4",
              "goals": {
                "for": "14",
                "against": "13"
              },
              "points": "17"
            },
            "team": {
              "id": "5d4443645ff25017160ebc92",
              "name": "Espanyol"
            }
          },
          {
            "position": {
              "current": "12",
              "change": "1"
            },
            "stats": {
              "win": "3",
              "draw": "6",
              "loss": "3",
              "goals": {
                "for": "14",
                "against": "12"
              },
              "points": "15"
            },
            "team": {
              "id": "5d443ed45ff250100c7d25e6",
              "name": "Villarreal"
            }
          },
          {
            "position": {
              "current": "13",
              "change": "-1"
            },
            "stats": {
              "win": "3",
              "draw": "6",
              "loss": "4",
              "goals": {
                "for": "13",
                "against": "19"
              },
              "points": "15"
            },
            "team": {
              "id": "5d443efd5ff250100c7d25e7",
              "name": "Mallorca"
            }
          },
          {
            "position": {
              "current": "14",
              "change": "3"
            },
            "stats": {
              "win": "4",
              "draw": "1",
              "loss": "7",
              "goals": {
                "for": "8",
                "against": "15"
              },
              "points": "13"
            },
            "team": {
              "id": "5d443e265ff2500f1b4d1985",
              "name": "Alavés"
            }
          },
          {
            "position": {
              "current": "15",
              "change": "0"
            },
            "stats": {
              "win": "3",
              "draw": "3",
              "loss": "7",
              "goals": {
                "for": "13",
                "against": "17"
              },
              "points": "12"
            },
            "team": {
              "id": "5d4323ad5ff25004850f5272",
              "name": "Celta Vigo"
            }
          },
          {
            "position": {
              "current": "16",
              "change": "2"
            },
            "stats": {
              "win": "2",
              "draw": "6",
              "loss": "5",
              "goals": {
                "for": "12",
                "against": "19"
              },
              "points": "12"
            },
            "team": {
              "id": "5d512f129dc6d66b4128bae2",
              "name": "Cádiz"
            }
          },
          {
            "position": {
              "current": "17",
              "change": "-3"
            },
            "stats": {
              "win": "2",
              "draw": "5",
              "loss": "5",
              "goals": {
                "for": "11",
                "against": "16"
              },
              "points": "11"
            },
            "team": {
              "id": "5d443e125ff2500f1b4d1982",
              "name": "Granada"
            }
          },
          {
            "position": {
              "current": "18",
              "change": "-2"
            },
            "stats": {
              "win": "2",
              "draw": "5",
              "loss": "6",
              "goals": {
                "for": "11",
                "against": "17"
              },
              "points": "11"
            },
            "team": {
              "id": "5d5198659dc6d6759f4e23ef",
              "name": "Elche"
            }
          },
          {
            "position": {
              "current": "19",
              "change": "0"
            },
            "stats": {
              "win": "0",
              "draw": "6",
              "loss": "7",
              "goals": {
                "for": "12",
                "against": "25"
              },
              "points": "6"
            },
            "team": {
              "id": "5d443e205ff2500f1b4d1984",
              "name": "Levante"
            }
          },
          {
            "position": {
              "current": "20",
              "change": "0"
            },
            "stats": {
              "win": "1",
              "draw": "3",
              "loss": "9",
              "goals": {
                "for": "6",
                "against": "19"
              },
              "points": "6"
            },
            "team": {
              "id": "5d443e1d5ff2500f1b4d1983",
              "name": "Getafe"
            }
          }
        ]
      }
    ]
  }
}
```

### Tables fields

All information related to Tables and standings will be returned nested within `tables` object.

{%hint warning%}
Tables are only available for **Football and Basketball** at the moment. If you use the `&include=tables` parameter in other sports it won't be shown.
{%endhint%}

| Field         | Meaning                                                                                                                                                                                       |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `available`   | <p>Boolean indicating if the league table is available or not. </p><p></p><p>If you don't have the required scopes will return <code>false</code> even if it's available in our coverage.</p> |
| `last_update` | Last update timestamp.                                                                                                                                                                        |
| `data`        | Nested tables available for the league.                                                                                                                                                       |




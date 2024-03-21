---
title: Shields and pictures
description: Get team shields and player pictures with just the ID.
---

If you have already called the [Teams and players](/the-basics/teams-and-players "Teams and players endpoint") endpoint you may have noticed that there is no information related to images.

Here is how you can get them. During trial periods, your access to shields may be limited, please check [Scope and trial accounts](/references/scope-and-trial-accounts) for more information about.

To download a shield you'll need 4 different values.
* The type: `teams` for a team shield or `players` for a person photo.
* The size, `b`, `m` or `s`. Details are listed in the table below.
* The team ID, that can be found using the [Teams and players](/the-basics/teams-and-players "Teams and players endpoint") endpoint.
* Format: `png` and `webp` for all teams except for national teams, that are only shown in `svg`.

### Available sizes and formats
| Size name | Team type | Pixels | Formats |
| --------------------- | ------------- | ------------------------------------------ | ------------------- |
| `b` (medium) | Teams & Players | 100x100 | `png`, `webp` |
| `m` (medium) | Teams & Players | 50x50 | `png`, `webp` |
| `s` (medium) | Teams & Players | 20x20 | `png`, `webp` |
| no size | National teams | Vectorial | `svg` |

### Endpoint for teams shields
`https://cdn.scrapebet.com/teams/[size]/[id].[format]`

Example picture for **Rafael Nadal**:
| Size `b`, format `webp` | Size `m`, format `png` | Size `s`, format `png` |
| --------------------- | ------------- | ------------------------------------------ |
| <img src="https://cdn.casasdeapuestas.com/teams/b/5d443c4d5ff2500bea24e964.webp" width="100px" height="100px" loading="lazy"> | <img src="https://cdn.casasdeapuestas.com/teams/m/5d443c4d5ff2500bea24e964.png" width="50px" height="50px" loading="lazy"> | <img src="https://cdn.casasdeapuestas.com/teams/s/5d443c4d5ff2500bea24e964.png" width="20px" height="20px" loading="lazy">  |
<br/>

Links that you should follow to download these pictures:
* **Big picture:** `https://cdn.casasdeapuestas.com/teams/b/5d443c4d5ff2500bea24e964.webp`
* **Medium picture:** `https://cdn.casasdeapuestas.com/teams/m/5d443c4d5ff2500bea24e964.png`
* **Small picture:** `https://cdn.casasdeapuestas.com/teams/s/5d443c4d5ff2500bea24e964.png`

### Endpoint for players photos
`https://cdn.scrapebet.com/players/[size]/[id].[format]`

Example picture for **Rafael Nadal**:
| Size `b`, format `png` | Size `m`, format `webp` | Size `s`, format `webp` |
| --------------------- | ------------- | ------------------------------------------ |
| <img src="https://cdn.scrapebet.com/players/b/5d5f16e79dc6d629091cf3b3.png" width="100px" height="100px" loading="lazy"> | <img src="https://cdn.scrapebet.com/players/m/5d5f16e79dc6d629091cf3b3.webp" width="50px" height="50px" loading="lazy"> | <img src="https://cdn.scrapebet.com/players/b/5d5f16e79dc6d629091cf3b3.png" width="20px" height="20px" loading="lazy">  |
<br/>

Links that you should follow to download these pictures:
* **Big picture:** `https://cdn.scrapebet.com/players/b/5d5f16e79dc6d629091cf3b3.png`
* **Medium picture:** `https://cdn.scrapebet.com/players/m/5d5f16e79dc6d629091cf3b3.webp`
* **Small picture:** `https://cdn.scrapebet.com/players/s/5d5f16e79dc6d629091cf3b3.webp`

### Endpoint for national teams
`https://cdn.scrapebet.com/flags/[Country ISO-2 code lowercase].svg`

Example picture for **United States**:
| 100x100 | 50x50 | 20x20 |
| --------------------- | ------------- | ------------------------------------------ |
| <img src="https://cdn.scrapebet.com/flags/us.svg" loading="lazy" title="US flag, unlimited size. This is a vector." width="100" height="100"> | <img src="https://cdn.scrapebet.com/flags/us.svg" loading="lazy" title="US flag, unlimited size. This is a vector." width="50" height="50"> | <img src="https://cdn.scrapebet.com/flags/us.svg" loading="lazy" title="US flag, unlimited size. This is a vector." width="20" height="20"> |
<br/>

Links that you should follow to download these pictures:
* **Any size:** `https://cdn.scrapebet.com/flags/us.svg`

We have all countries flags in our CDN, however, that doesn't means all of them have available leagues or teams. Check [Countries](/the-basics/countries) to download all the available countries.

{%hint danger%}If the shield is not available for some  reason, a 404 HTTP code will be returned. Remember that you can check if a team/player has a shield available with the `has_shield` field in the teams endpoint.{%endhint%}

### Cache times & Refreshing cache
The shields are cached up to 1 year in edge and 30 days in browser-cache. If you need to refresh the shields cache feel free to use any query parameter among the URL and the newest version will show up.

### Point your domain to our CDN
If preferred, it's possible to point your own subdomain or domain to our CDN instead of downloading all pictures or using our domain. This service has an additional cost and depends on the monthly number of requests.

This is the recommended option, that will also ensure that shields will always be up-to-date.

To get a custom domain or point your domain to our CDN, please [talk to your sales agent](https://scrapebet.com/contact).
# ⚽ World Cup 2026 — Build Day Data Pack

> 🇰🇷 한국어: [README.ko.md](README.ko.md)

> Everything you need to build, in one place. The core sources need **no API key, no signup.** Road to ICML 2026 Seoul.

## 📖 Two kinds of data
- **✅ Static (given as files · works offline)** — all 104 matches, scores, goals · 12 groups · 48-team squads · 16 stadiums · teams + flag emoji · World Bank GDP/population
- **🌐 Live / keyed (given as URLs)** — live scores · weather · odds. Live data can't be frozen into a file — that's why it's a link.

## 🚀 30-second start — no key
```js
const data = await fetch("https://raw.githubusercontent.com/openfootball/worldcup.json/master/2026/worldcup.json").then(r => r.json())
// data.matches = 104 matches.  Score = m.score.ft = [home, away]   ⚠️ NOT score1/score2
// same folder: worldcup.groups.json · worldcup.squads.json · worldcup.stadiums.json · worldcup.teams.json (flag emoji + FIFA code)
```
> ⚠️ **The #1 trap**: scores live under `m.score.ft`, goals under `m.goals1`/`m.goals2`. Read `score1`/`score2` and you'll see 0 results.

## 🌐 Where to look (no key unless noted)
| What | URL | Note |
|---|---|---|
| Live scores (today) | `site.api.espn.com/apis/site/v2/sports/soccer/fifa.world/scoreboard` | unofficial ESPN, no key — strongest live |
| Live fallback | `worldcup26.ir/get/games` | no key |
| Stadium weather | `api.open-meteo.com/v1/forecast` | no key |
| Flag images | `flagcdn.com/w320/br.png` | lowercase ISO code |
| GDP / population | `api.worldbank.org/v2/country/all/indicator/NY.GDP.MKTP.CD?format=json` | no key |
| Historical xG (~2022) | `github.com/statsbomb/open-data` | free, attribution |
| Odds / clean fixtures | `football-data.org` · `the-odds-api.com` | **free key required** — bonus only |

## 🚫 Don't waste time on
API-Football free (2026 blocked) · X (Twitter) API search (dead for free → Reddit/Bluesky) · national crests & player photos (no free/legal source → use flag emoji + jersey number) · KickoffAPI (dead, 404)

## 🤖 Codex
- Default: **"Sign in with ChatGPT"** (your plan's limits)
- With an **API credit code**: `platform.openai.com` → Billing → **Promotions → "Add a promotional credit"** → code → **API keys → Create** → sign into Codex with the **API key** (❗not ChatGPT — that's how the credit gets used). No card → it just stops when the credit runs out.

## 💡 Ideas
🎤 over-the-top AI commentary bot · 🔮 Round-of-32 qualifier predictor (48 teams · 8 third-place spots) · 📊 live scoreboard · 🎲 a model that's confidently wrong · 🌧 16-stadium weather map · 😏 trash-talk data bot ("Group of Death by GDP")

---
*Offline full pack (data files + single-file viewer HTML) is in the Telegram `.zip` or this repo's `data/` folder.*
*No prizes, no judges — build something dumb & delightful. Drop a 15–30s clip in Telegram — that's your intro.*

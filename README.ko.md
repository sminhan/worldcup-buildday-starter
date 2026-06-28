> 🇬🇧 English: [README.md](README.md)

# ⚽ World Cup 2026 — Build Day Data Pack

> 빌드에 필요한 데이터, 한 곳에. 핵심은 **키·가입 없이.** Road to ICML 2026 Seoul.

## 📖 데이터는 두 종류
- **✅ 정적 (파일로 줌 · 오프라인)** — 104경기·점수·골 · 12개조 · 48팀 명단 · 16구장 · 팀+국기 이모지 · World Bank GDP/인구
- **🌐 라이브/키 (주소로 줌)** — 실시간 스코어 · 날씨 · 배당. 라이브는 박제 못 해서 **링크**.

## 🚀 30초 시작 — 키 없음
```js
const data = await fetch("https://raw.githubusercontent.com/openfootball/worldcup.json/master/2026/worldcup.json").then(r => r.json())
// data.matches = 104경기.  점수 = m.score.ft = [홈, 원정]   ⚠️ score1/score2 아님!
// 같은 폴더: worldcup.groups.json · worldcup.squads.json · worldcup.stadiums.json · worldcup.teams.json(국기 이모지·FIFA코드)
```
> ⚠️ **1순위 함정**: 점수는 `m.score.ft`, 골은 `m.goals1`/`m.goals2`. `score1`/`score2`로 읽으면 결과가 0으로 보임.

## 🌐 더 찾아볼 곳 (표시 없으면 키 불필요)
| 무엇 | 주소 | 메모 |
|---|---|---|
| 실시간 스코어(오늘) | `site.api.espn.com/apis/site/v2/sports/soccer/fifa.world/scoreboard` | 비공식 ESPN, 키 없음 — 가장 강력 |
| 라이브 폴백 | `worldcup26.ir/get/games` | 키 없음 |
| 구장 날씨 | `api.open-meteo.com/v1/forecast` | 키 없음 |
| 국기 이미지 | `flagcdn.com/w320/br.png` | 소문자 ISO 코드 |
| GDP·인구 | `api.worldbank.org/v2/country/all/indicator/NY.GDP.MKTP.CD?format=json` | 키 없음 |
| 역사 xG (~2022) | `github.com/statsbomb/open-data` | 무료·출처표기 |
| 배당·깔끔 일정 | `football-data.org` · `the-odds-api.com` | **무료 키 필요** — 보너스 |

## 🚫 시간 낭비 금지
API-Football 무료(2026 막힘) · X(트위터) API 검색(무료 사망 → Reddit/Bluesky) · 국가대표 엠블럼·선수사진(무료/합법 소스 없음 → 국기 이모지 + 등번호) · KickoffAPI(죽음 404)

## 🤖 Codex
- 기본: **"Sign in with ChatGPT"** (본인 플랜 한도)
- **API 크레딧 코드** 받았으면: `platform.openai.com` → Billing → **Promotions → "Add a promotional credit"** → 코드 → **API keys → Create** → Codex에 **API 키로 로그인**(❗ChatGPT 아님 — 그래야 크레딧 차감). 카드 없으면 소진 시 멈춤.

## 💡 아이디어
🎤 과몰입 AI 중계봇 · 🔮 32강 진출 예측기(48팀·3위 8자리) · 📊 라이브 스코어보드 · 🎲 자신만만 틀리는 예측모델 · 🌧 16구장 날씨지도 · 😏 드립 데이터봇("GDP로 보는 죽음의 조")

---
*오프라인 전체 팩(데이터 파일 + 단일 뷰어 HTML)은 텔레그램 `.zip` 또는 이 repo `data/` 폴더에서.*
*No prizes, no judges — build something dumb & delightful. 만든 건 텔레그램에 15–30초 영상으로.*

# Serper Web Search Skill

Google search API via serper.dev.

## Quick Search (curl)

```bash
# Basic web search
curl -s -X POST "https://google.serper.dev/search" -H "X-API-KEY: $SERPER_API_KEY" -H "Content-Type: application/json" -d '{"q": "AI energy consumption research 2025"}' | jq '.organic[:5] | .[] | {title, link, snippet}'

# News search
curl -s -X POST "https://google.serper.dev/news" -H "X-API-KEY: $SERPER_API_KEY" -H "Content-Type: application/json" -d '{"q": "ChatGPT carbon footprint"}' | jq '.news[:5] | .[] | {title, link, date}'

# Scholar search
curl -s -X POST "https://google.serper.dev/scholar" -H "X-API-KEY: $SERPER_API_KEY" -H "Content-Type: application/json" -d '{"q": "large language model energy efficiency"}' | jq '.organic[:5] | .[] | {title, link, citedBy}'

# Image search
curl -s -X POST "https://google.serper.dev/images" -H "X-API-KEY: $SERPER_API_KEY" -H "Content-Type: application/json" -d '{"q": "AI data center energy"}' | jq '.images[:3] | .[] | {title, imageUrl}'
```

## Endpoints

| Endpoint | Use |
|----------|-----|
| `/search` | Web results |
| `/news` | News articles |
| `/scholar` | Academic papers |
| `/images` | Images |

## Options

```json
{
  "q": "search query",
  "num": 10,
  "gl": "us",
  "hl": "en",
  "tbs": "qdr:m"
}
```

Time filters: `qdr:d` (day), `qdr:w` (week), `qdr:m` (month), `qdr:y` (year)

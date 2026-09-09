---
name: curl-search
type: page
about: One-liner and script-based web search using curl.
---

# Web Search — curl

## Basic Search

```bash
curl -s "https://html.duckduckgo.com/html/?q=<your+query>"
```

Pipe to `grep` to extract result titles:

```bash
curl -s "https://html.duckduckgo.com/html/?q=python+web+scraping" \
  | grep -o '<a class="result__a"[^>]*>[^<]*</a>' \
  | sed 's/<[^>]*>//g'
```

## Extract URLs with grep/sed

```bash
curl -s "https://html.duckduckgo.com/html/?q=<query>" \
  | grep -oP 'href="https?://[^"]+"' \
  | sed 's/href="//;s/"//' \
  | head -10
```

## URL-Encode Query

```bash
QUERY=$(python3 -c "import urllib.parse; print(urllib.parse.quote('$1'))")
curl -s "https://html.duckduckgo.com/html/?q=${QUERY}"
```

Or with `jq`:

```bash
curl -s "https://html.duckduckgo.com/html/?q=$(echo "$QUERY" | jq -sRr @uri)"
```

## Shell Script Wrapper

```bash
#!/bin/bash
# search.sh — minimal DuckDuckGo search via curl

QUERY=$(python3 -c "import urllib.parse; import sys; print(urllib.parse.quote(sys.argv[1]))" "$1")
curl -s "https://html.duckduckgo.com/html/?q=${QUERY}" \
  | grep -oP '(?<=<a class="result__a" href=")[^"]+' \
  | head "${2:-10}"
```

Usage: `search.sh "python web scraping" 5`

## Limitations

- HTML parsing with shell tools is fragile — the HTML structure may change
- For production use, prefer the Python approach (see **python-search** page)

---
name: ddgr-pattern
type: page
about: How ddgr scrapes DuckDuckGo HTML — reference architecture for writing a custom search script.
---

# Web Search — ddgr Pattern

`ddgr` is a CLI tool that scrapes DuckDuckGo's HTML results page. Understanding how it works gives you the pattern for writing your own search implementation.

## DuckDuckGo HTML Endpoint

```
https://html.duckduckgo.com/html/?q=<url-encoded-query>
```

No API key required. Returns a plain HTML results page.

## URL Construction

```python
from urllib.parse import urlencode

query = "python web scraping"
url = f"https://html.duckduckgo.com/html/?{urlencode({'q': query})}"
# https://html.duckduckgo.com/html/?q=python+web+scraping
```

## Response Parsing

The HTML returned has a consistent structure. Each result lives in an `<a>` tag with class `result__a`. Extract the title, URL, and snippet.

```python
import re

# Simple regex-based extraction (no BeautifulSoup needed)
pattern = r'<a class="result__a" href="([^"]+)">([^<]+)</a>.*?<a class="result__snippet"[^>]*>([^<]+)</a>'

for match in re.finditer(pattern, html, re.DOTALL):
    url, title, snippet = match.groups()
    results.append({"title": title, "url": url, "snippet": snippet})
```

## Key Considerations

- **User-Agent** — set a real browser UA to avoid 403s: `{"User-Agent": "Mozilla/5.0"}`
- **Rate limiting** — add `time.sleep(1)` between requests to avoid IP blocks
- **No guarantees** — DuckDuckGo may change HTML structure; regex or parser may need updating
- **Alternatives** — `https://lite.duckduckgo.com/50x/` is a lighter mobile-friendly variant

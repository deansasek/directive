---
name: python-search
type: page
about: Python requests wrapper for DuckDuckGo HTML search.
---

# Web Search — Python

## Basic Implementation

```python
import re
import time
import requests
from urllib.parse import urlencode
from dataclasses import dataclass

@dataclass
class SearchResult:
    title: str
    url: str
    snippet: str

def search(query: str, num: int = 10, delay: float = 1.0) -> list[SearchResult]:
    """
    Search DuckDuckGo HTML and return structured results.
    No API key required.
    """
    url = f"https://html.duckduckgo.com/html/?{urlencode({'q': query})}"
    headers = {"User-Agent": "Mozilla/5.0 (compatible; Python/3)"}

    r = requests.get(url, headers=headers)
    r.raise_for_status()

    results = []

    # Extract result blocks
    result_pattern = re.compile(
        r'<a class="result__a" href="(?P<url>[^"]+)">(?P<title>[^<]+)</a>.*?'
        r'<a class="result__snippet"[^>]*>(?P<snippet>[^<]+)</a>',
        re.DOTALL
    )

    for match in result_pattern.finditer(r.text):
        results.append(SearchResult(
            title=match.group('title').strip(),
            url=match.group('url').strip(),
            snippet=re.sub(r'<[^>]+>', '', match.group('snippet')).strip()
        ))
        if len(results) >= num:
            break

    time.sleep(delay)  # rate limit
    return results
```

## Usage

```python
results = search("python web scraping best practices", num=5)
for r in results:
    print(f"{r.title}\n  {r.url}\n  {r.snippet}\n")
```

## Error Handling

```python
def safe_search(query: str, num: int = 10) -> list[SearchResult]:
    try:
        return search(query, num)
    except requests.HTTPError as e:
        if e.response.status_code == 403:
            raise RuntimeError("Rate limited or blocked — try a different User-Agent or delay")
        raise RuntimeError(f"HTTP error {e.response.status_code}") from e
    except requests.RequestException as e:
        raise RuntimeError(f"Request failed: {e}") from e
```

## With BeautifulSoup (Alternative Parser)

```python
from bs4 import BeautifulSoup

def search_bs(query: str, num: int = 10) -> list[SearchResult]:
    url = f"https://html.duckduckgo.com/html/?{urlencode({'q': query})}"
    r = requests.get(url, headers={"User-Agent": "Mozilla/5.0"})
    soup = BeautifulSoup(r.text, "html.parser")

    results = []
    for a in soup.select("a.result__a")[:num]:
        results.append(SearchResult(
            title=a.get_text(strip=True),
            url=a["href"],
            snippet=""
        ))
    return results
```

Install: `pip install beautifulsoup4 requests`

## Production Considerations

- **User-Agent rotation** — vary the UA string to reduce blocking risk
- **Rate limiting** — always add `time.sleep(delay)` between calls (1–2 seconds)
- **Proxy support** — pass `proxies={"https": "http://proxy:8080"}` to `requests.get()`
- **No stability guarantee** — DuckDuckGo HTML structure may change without notice; keep parser updated

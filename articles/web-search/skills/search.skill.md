---
name: search
type: skill
about: Runs a web search via DuckDuckGo HTML scraping (no API key).
---

# Search

Search the web using DuckDuckGo's HTML interface — no API key required.

**Arguments:**
- `query` — search query string
- `num` — number of results to return (default 10)

**Behavior:**
1. Constructs DuckDuckGo HTML URL with URL-encoded query
2. Executes HTTP GET with a browser User-Agent header
3. Parses HTML to extract title, URL, and snippet per result
4. Returns structured results as a list

**Output:**
```
- <title>
  URL: <url>
  Snippet: <snippet>
```

**Example:**
```
search("python web scraping best practices", num=5)
```

**Notes:**
- Rate-limit calls with ~1 second delay between requests
- If blocked (403), try varying the User-Agent header
- For production use, consider a paid search API (SerpAPI, Tavily) for stability

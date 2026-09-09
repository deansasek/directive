---
name: restful-apis-overview
type: page
about: RESTful API architecture — resource modeling, HTTP semantics, payload design, versioning, security, and resiliency.
---

# RESTful APIs

## Core Architectural Principles

### Resource-Oriented URIs

Use plural nouns for resources (`/v1/accounts`). Avoid action verbs in URIs (`/v1/create-account`); rely on HTTP methods to express intent.

### Statelessness

Request instances must contain full contextual authentication and state. Do not rely on server-side session persistence.

### Content Negotiation

Require explicit `Accept` and `Content-Type` headers (`application/json`).

### HATEOAS / Self-Describing Payload

Include navigational links (`_links`) in responses to decouple client mechanics from hardcoded paths when applicable.

## HTTP Method & Status Code Matrix

| HTTP Method | Idempotent | Safe | Primary Success Code | Typical Error Codes |
|-------------|-----------|------|---------------------|---------------------|
| GET | Yes | Yes | 200 OK | 404 Not Found, 400 Bad Request |
| POST | No | No | 201 Created | 400 Bad Request, 409 Conflict, 422 Unprocessable |
| PUT | Yes | No | 200 OK / 204 No Content | 400 Bad Request, 404 Not Found |
| PATCH | No | No | 200 OK / 204 No Content | 400 Bad Request, 409 Conflict |
| DELETE | Yes | No | 200 OK / 204 No Content | 404 Not Found |

## Essential HTTP Status Codes

### 2xx Success

- **200 OK** — Standard payload
- **201 Created** — Must include `Location` header
- **202 Accepted** — Async/queued
- **204 No Content** — Delete/Update success without body

### 4xx Client Errors

- **400 Bad Request** — Malformed syntax
- **401 Unauthorized** — Missing/invalid auth token
- **403 Forbidden** — Authenticated but insufficient scopes
- **404 Not Found** — Missing resource
- **409 Conflict** — State collision/duplicate keys
- **422 Unprocessable Entity** — Valid JSON, failed business/validation rules
- **429 Too Many Requests** — Rate limited

### 5xx Server Errors

- **500 Internal Server Error** — Unhandled exception (strip stack traces in prod)
- **502 Bad Gateway** — Upstream service failure
- **503 Service Unavailable** — Circuit breaker active/maintenance

## URI Hierarchy & Naming Conventions

- Use **kebab-case** for URIs: `/v1/payment-methods`
- Use **camelCase** or **snake_case** consistently for JSON payload keys across all services
- Nest child resources **up to 1 level max**

**Recommended:** `GET /v1/organizations/{orgId}/members`

**Avoid deep nesting:** `GET /v1/organizations/{orgId}/departments/{deptId}/teams/{teamId}/members`

**Alternative for deep scope:** `GET /v1/members?organizationId={orgId}&teamId={teamId}`

## Payload Design Standards

### Enveloping & Collections (Pagination)

Never return top-level arrays. Always return top-level JSON objects to allow metadata extension without breaking client schema parsing.

```json
{
  "data": [
    {
      "id": "usr_998231a",
      "email": "alex.dev@enterprise.io",
      "status": "active"
    }
  ],
  "pagination": {
    "limit": 20,
    "startingAfter": "usr_998231a",
    "hasMore": true,
    "totalRecords": 1420
  }
}
```

## RFC 7807 Standardized Error Format

Return predictable error envelopes for non-2xx responses.

```json
{
  "type": "https://api.enterprise.io/errors/invalid-payload",
  "title": "Validation Failed",
  "status": 422,
  "detail": "The payload contains field errors preventing execution.",
  "instance": "/v1/transfers/tr_88201",
  "code": "ERR_VALIDATION_FAILURE",
  "invalidParams": [
    {
      "name": "amount",
      "reason": "Must be greater than 0.00"
    }
  ]
}
```

## Versioning Strategies

| Strategy | Pattern | Best For | Trade-offs |
|---------|---------|---------|-----------|
| URI Path (Recommended) | `/v1/customers` | External/Public APIs | Highly visible; easy to route via API Gateways |
| Header (Custom) | `X-API-Version: 2026-09-01` | Internal Microservices | Clean URIs; harder to cache at browser/CDN layer |
| Content Negotiation | `Accept: application/vnd.company.v2+json` | Pure REST / HATEOAS | Strict compliance; complex client implementation |

## Resiliency, Security & Observability

### Idempotency Keys

For POST mutation endpoints (e.g., payments), support an `Idempotency-Key: <UUID>` header. Cache the response against the key for 24 hours to prevent duplicate execution during network retries.

### Rate-Limit Tracking

Expose state via standard headers:

- `X-RateLimit-Limit: 10000`
- `X-RateLimit-Remaining: 9840`
- `X-RateLimit-Reset: 1788739200`
- `Retry-After: 120` — Required on 429 responses

### Distributed Tracing

Require and propagate `X-Request-ID` or W3C `traceparent` headers through API gateways to downstream services.

---
name: cors-suspect
description: Use this skill whenever CORS configuration is read, written, or suggested — Access-Control-Allow-Origin headers, Express `cors({ ... })`, Flask `CORS(...)`, Fastify `@fastify/cors`, Koa `@koa/cors`, FastAPI `CORSMiddleware`, `.htaccess` Access-Control directives, CloudFront response headers policies, nginx `add_header Access-Control-*`, or anything that echoes the request's Origin header. Always assumes the worst interpretation (wildcard origin, credentials true, reflected origin, missing Vary), names the specific line, and proposes a tightened config.
---

# CORS Suspect

Every CORS config is guilty until proven innocent. You read it assuming the worst. Then you read it again, carefully.

## When to trigger

Auto-invoke when code in the edit window or the current context touches:

- Express: `cors({...})`, `app.use(cors(...))`
- Flask: `flask_cors.CORS(...)` or `@cross_origin(...)`
- FastAPI / Starlette: `CORSMiddleware(...)`
- Fastify: `@fastify/cors`
- Koa: `@koa/cors`
- Django: `django-cors-headers` settings (`CORS_ALLOWED_ORIGINS`, `CORS_ALLOW_ALL_ORIGINS`)
- Go: `github.com/rs/cors`, `gin-contrib/cors`, `gorilla/handlers` CORS
- Raw headers: `Access-Control-Allow-Origin`, `Access-Control-Allow-Credentials`, `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers`, `Access-Control-Expose-Headers`
- Infra: `add_header Access-Control-Allow-Origin` in nginx, CloudFront response-headers policies, API Gateway CORS
- Any code that does `res.setHeader("Access-Control-Allow-Origin", req.headers.origin)` (reflected origin)

## Required shape

```
[ suspect in custody ]

<one-sentence naming the specific footgun on a specific file:line.
 always interpret the config uncharitably.>

THE RISK
  <one sentence. who gets what, in plain terms.
  e.g. "any site the user visits can read this API with their cookies">

THE FIX
  <a code block with the tightened config. exact drop-in.>

CHECKLIST
  - [ ] origin is an explicit allowlist, not `*` and not reflected
  - [ ] `credentials: true` only paired with an allowlist
  - [ ] methods and headers enumerated, not `*`
  - [ ] `Vary: Origin` on any response where the origin varies
  - [ ] preflight cache (`Access-Control-Max-Age`) is reasonable
```

## The suspect patterns

| Pattern | One-liner |
|---|---|
| `origin: "*"` + `credentials: true` | *"wildcard plus credentials. browsers will refuse this, but the intent alone is incriminating."* |
| Reflected origin (`res.setHeader("ACAO", req.headers.origin)`) without an allowlist check | *"you are allowing everyone. a reflected origin is a wildcard in a trench coat."* |
| `origin: true` in Express `cors` middleware | *"`origin: true` mirrors the request origin. that is the same as wildcard, just quieter."* |
| `CORS_ALLOW_ALL_ORIGINS = True` in Django with auth | *"django says yes to everyone. the session middleware says yes too. we have a problem."* |
| Allowlist includes `http://localhost` in production | *"localhost is in the production allowlist. the production allowlist is a diary."* |
| Missing `Vary: Origin` with a dynamic origin | *"caches are going to mix responses. the CDN is going to get creative."* |
| `methods: "*"` or `allowedHeaders: "*"` | *"`*` is the same word as `i have not thought about this`. enumerate."* |
| `Access-Control-Max-Age` absent or very low | *"every request becomes two requests. the preflight cache exists for a reason."* |

## Voice

- *"suspect in custody."*
- *"the origin header is client-controlled. treat it accordingly."*
- *"you trust the browser. the browser trusts the user. the user trusts a bookmark."*
- Short. Specific. Paranoid.

## The fix (always give a drop-in)

When you propose a fix, produce a real, tightened config in the same library the user is using. Not pseudo-code. Not *"use an allowlist"* — the literal allowlist array, with the user's actual domains if you can see them in the repo (env vars, README, `vercel.json`, etc.), or a `FIXME: <your domains here>` placeholder labeled as such.

## Hard rules

1. **Always uncharitable.** If the config *can* be read as over-permissive, read it that way. The user can argue back.
2. **Name the file and line.** *"`src/server.ts:34`."*
3. **Give a drop-in fix.** Not advice. A replacement code block.
4. **Flag `credentials: true` specifically.** This combo is the most common footgun; never skip the check.
5. **After the suspicion, help.** This is a skill, not an agent. You flag, you fix, you step aside.
6. **Break character for real incidents.** *"we just noticed prod has `origin: *` with credentials"* → drop the bit, walk them through: tighten config, deploy, then audit logs for any cross-origin reads that already happened.

## Worked example

**Code in context** (`src/server.ts:34`):
```ts
app.use(cors({ origin: true, credentials: true }));
```

**Skill output**:
```
[ suspect in custody ]

`src/server.ts:34`. `origin: true` with `credentials: true`.
that is "any site that reaches the user's browser can read this
API with the user's cookies", dressed in a boolean.

THE RISK
  any page the user visits — phishing, ad network, random blog —
  can make authenticated requests to this API on their behalf and
  read the responses.

THE FIX
  const ALLOWED = [
    "https://app.example.com",
    "https://staging.example.com",
    // FIXME: add / remove your real origins here
  ];

  app.use(cors({
    origin: (origin, cb) =>
      !origin || ALLOWED.includes(origin)
        ? cb(null, true)
        : cb(new Error("not allowed by CORS")),
    credentials: true,
    methods: ["GET", "POST", "PUT", "PATCH", "DELETE"],
    allowedHeaders: ["Authorization", "Content-Type"],
    maxAge: 600,
  }));

CHECKLIST
  - [x] origin is an explicit allowlist
  - [x] credentials only with allowlist
  - [x] methods + headers enumerated
  - [ ] confirm `Vary: Origin` is on responses (Express `cors` handles this, but double-check a CDN isn't stripping it)
  - [x] preflight cache set to 10 minutes
```

---

*Note: cors-suspect is a Gloat Goat Blackhat parody skill. The paranoia is theater; the checklist and the drop-in fix are real. CORS is a browser-side control — for defense in depth, also require a proper auth check on every endpoint.*

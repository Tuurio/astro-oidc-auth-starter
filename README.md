# Astro OIDC Auth Starter

Astro authentication starter for Tuurio ID with protected server routes and standards-based OpenID Connect.

[![Verify template](https://github.com/Tuurio/astro-oidc-auth-starter/actions/workflows/verify.yml/badge.svg)](https://github.com/Tuurio/astro-oidc-auth-starter/actions/workflows/verify.yml)

> Generated from [`Tuurio/auth_samples/auth_samples_astro`](https://github.com/Tuurio/auth_samples/tree/main/auth_samples_astro). Submit implementation fixes upstream so they are not replaced by the next synchronized release.

## What you get

- Standards-based OpenID Connect authentication with framework-native integration.
- Exact redirect and post-logout redirect handling.
- Protected-route and logout examples.
- A reviewed, pinned Tuurio provisioning workflow.

## Quickstart

1. Create a repository with **Use this template** or clone this repository.
2. Follow the framework-specific prerequisites below.
3. Review and run this pinned provisioning command:

```bash
npx manage-tuurio-id@1.1.6 init --framework astro --project-dir . --auth browser --yes --output json --campaign github_astro --no-open --no-wait
```

4. Approve the exact command, then complete the secure browser handoff yourself.
5. Run the build and verify one real sign-in and sign-out.

Never paste credentials, client secrets, authorization codes, tokens, session cookies, or environment-file contents into an agent chat. Browser and native applications are public clients and must not contain a client secret.

## Runtime and verification

- Runtime: Node.js 24.11+
- Package manager: npm
- Verification: `npm ci && npm run check && npm run build`

## Security model

This starter uses OpenID Connect Authorization Code flow. Browser and native clients use PKCE S256 and contain no client secret. Redirect and post-logout redirect URIs must match exactly. Identity comes from the established OIDC integration or an authenticated UserInfo request; decoded JWT payloads are never treated as validation. Keep generated local environment files ignored and never commit tokens or credentials.

## Framework instructions

# Astro OIDC authentication with Tuurio ID

Runnable Astro Node-server starter with Authorization Code + PKCE S256, validated ID tokens, UserInfo subject binding, opaque server-side sessions, a protected page, and RP-initiated logout.

## Configure

```bash
npx manage-tuurio-id@1.1.6 init --framework astro --project-dir . --auth browser --yes --output json --campaign github_astro --no-open --no-wait
npm install
npm run dev
```

The in-memory transaction/session stores are intentionally visible sample infrastructure. Replace them with a shared server-side store before horizontal scaling. Keep `TUURIO_CLIENT_SECRET` server-only.


## License

Licensed under the Apache License, Version 2.0. See [`LICENSE`](./LICENSE).

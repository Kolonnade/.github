# Kolonnade

A colonnade of identity packages. Each one is a column; **Portico** is the one at the entrance.

Portico is a passkey-first identity provider you run yourself, with the client libraries that go with it. It is written in Go, stores everything in PostgreSQL, and is built on [`zitadel/oidc`](https://github.com/zitadel/oidc) so the OAuth and OpenID Connect machinery comes from a maintained implementation rather than from us.

## What Portico gives you

- **Passkeys, and nothing else to remember.** WebAuthn enrolment, sign-in and recovery, with the credential-flag and sign-count rules that synced passkeys actually need.
- **One sign-in across your sites**, whether they sit on subdomains of one domain or on entirely different ones. No third-party cookies involved.
- **Several signed-in accounts at once**, numbered from 0 the way people already expect, with each site signed in as whichever account the person chose for it.
- **Sign-out that arrives**, through OpenID Connect Back-Channel Logout, and profile changes pushed to sites as Shared Signals events rather than waiting for the next token refresh.
- **Apps, not just websites.** OpenID Connect Native SSO, so a family of apps on one device share a sign-in without sharing a refresh token, plus native passkey ceremonies.
- **Extension points where your product differs.** The profile — display name, avatar, whatever your product means by it — is an interface with a default implementation, not something baked in.

## Repositories

| Repository | What it is | Status |
|---|---|---|
| `portico` | The provider and the website library, in Go | Not published yet |
| `portico-swift` | Sign-in for iOS and macOS | Planned |
| `portico-android` | Sign-in for Android | Later |

## Status

Early, and honest about it: the code is being rebuilt on `zitadel/oidc` before it is published, and the first tag will be a `v0.x` with the API still moving. Passing the OpenID Foundation's conformance suite is a release gate, not an aspiration for later.

Everything here is MIT licensed.

## Security

Please report vulnerabilities privately — see [SECURITY.md](https://github.com/Kolonnade/.github/blob/main/SECURITY.md). Identity software is exactly the kind where a quiet report and a coordinated fix beat a fast public issue.

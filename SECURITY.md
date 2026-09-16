# Security policy

Kolonnade's packages sign people in. A vulnerability here is someone else's account takeover, so please report privately and give us a chance to ship a fix before it is public.

## Reporting a vulnerability

Use **[private vulnerability reporting](https://docs.github.com/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability)** on the repository the problem is in: *Security* → *Report a vulnerability*. It creates a private thread with the maintainers.

If the repository somehow has it turned off, open a private report on [`Kolonnade/.github`](https://github.com/Kolonnade/.github/security/advisories/new) instead, and say which repository you mean.

**Please do not** open a public issue, a pull request or a discussion for a vulnerability.

A useful report has: what an attacker can do, the steps or a script that show it, the version or commit you tested, and anything about the deployment that matters (the database, the reverse proxy, the client type).

## What to expect

| | |
|---|---|
| Acknowledgment | Within three working days |
| First assessment | Within seven days, saying whether we think it is a vulnerability and how severe |
| Fix and advisory | As fast as the severity warrants, coordinated with you |
| Disclosure | A GitHub Security Advisory with a CVE, published when the fix ships or at 90 days, whichever is first, unless we agree otherwise |
| Credit | Yours by name or handle in the advisory, unless you would rather not be named |

There is no bug bounty. This is an unfunded project.

## Supported versions

Nothing is released yet. Until the first tagged release, the supported version is the default branch. When releases begin, this table will name the supported minor versions and how long each is supported.

## Scope

**In scope:** authentication and session handling, token issuance and verification, WebAuthn ceremonies, the storage layer, the relying-party libraries, the client packages, and anything in these repositories that a deployment relies on to be correct.

**Out of scope:** a deployment's own misconfiguration, vulnerabilities in dependencies that are already public and fixed upstream (tell us so we can bump them, but that is not an advisory here), denial of service by sheer traffic volume, and reports produced by a scanner without a demonstrated impact.

## For operators

Releases that fix a vulnerability are marked in the release notes and get an advisory. Watching a repository for **Releases** and **Security advisories** is the fastest way to hear about one. Running `govulncheck` in your own build is the most reliable way, because it reports only what your binary actually reaches.

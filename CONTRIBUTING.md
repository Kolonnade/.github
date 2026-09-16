# Contributing

Thanks for looking. This is a young project, so the most valuable contributions right now are the ones that stop us designing ourselves into a corner: a flow that doesn't work for your deployment, a spec we've read wrong, a threat we've missed.

## Before writing code

- **Something broken?** Open an issue with what you did, what happened and what you expected.
- **Something new?** Open an issue describing the problem before the solution. A pull request that arrives without one may be asking for something we deliberately left out, and neither of us enjoys finding that out at review time.
- **A vulnerability?** Don't open an issue. See [SECURITY.md](SECURITY.md).

Two rules of the project that are not up for negotiation, so you don't waste your time:

1. **Portico answers "who is this person", never "what may they do".** No roles, no permissions, no admin flags in the provider or in tokens. Authorization belongs to the application.
2. **Protocol code comes from `zitadel/oidc` wherever it can.** If a change reimplements something the library already does, it will be turned down.

## Working on it

```bash
go vet ./... && go test ./...
```

The Go repositories need PostgreSQL for their tests, and the tests **skip** without it rather than fail. A run where the integration tests skipped has proved nothing, so check the output, not just the exit code. Each repository's README says how to point the tests at a database.

Style, briefly:

- Write code that reads like the code around it.
- Comment the trap, not the syntax. "Backup Eligible is immutable after registration, and overwriting it breaks every later assertion" earns its place; "increment the counter" does not.
- A change in behavior comes with a test that fails without it.
- Keep the public API small. Anything not meant as API belongs under `internal/`.

## Commits and pull requests

- **Sign off every commit** — `git commit -s` — which certifies the [Developer Certificate of Origin](https://developercertificate.org/). There is no CLA.
- Commit messages: one imperative sentence on the first line, a blank line, then the why. Not the what; the diff already says that.
- Keep a pull request to one idea. Two ideas are two pull requests.
- Say how you tested it, and paste the output when it matters.

## Licensing

Contributions are accepted under the MIT license, the same one the projects use. By signing off, you confirm you have the right to contribute the code.

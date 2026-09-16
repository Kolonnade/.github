<!--
A vulnerability does not belong in a pull request either — see SECURITY.md.
-->

## What this changes

<!-- One paragraph. The diff says what; say why. -->

## How it was tested

<!-- The commands you ran and what you saw. "go test ./..." with the integration tests skipped is not a test run. -->

## Checklist

- [ ] Every commit is signed off (`git commit -s`), certifying the [DCO](https://developercertificate.org/)
- [ ] `go vet ./...` and `go test ./...` pass, with the database-backed tests actually running
- [ ] A change in behavior comes with a test that fails without it
- [ ] Public API changes are documented, and anything not meant as API is unexported or `internal/`
- [ ] Nothing here decides *what a person may do* — authorization stays with the application
- [ ] Nothing here reimplements what `zitadel/oidc` provides

## Related

<!-- Issue numbers, specifications, prior discussion. -->

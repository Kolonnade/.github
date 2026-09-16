# .github

Organization-wide defaults for [Kolonnade](https://github.com/Kolonnade).

| Path | What GitHub does with it |
|---|---|
| `profile/README.md` | The organization's public profile page |
| `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md` | Used by every repository in the organization that does not ship its own copy |
| `.github/ISSUE_TEMPLATE/` | Default issue forms |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default pull request template |
| `.github/workflows/go-ci.yml` | A reusable workflow the Go repositories call |

A repository that needs something different keeps its own copy of the file; this repository is only the fallback.

## Calling the reusable workflow

```yaml
jobs:
  ci:
    uses: Kolonnade/.github/.github/workflows/go-ci.yml@main
    with:
      go-version: '1.25'
```

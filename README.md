# ResoDesk org defaults

**This repository is public.** It holds only generic, non-sensitive files: no secrets, no internal hostnames, no
product or customer details.

| Path                                   | What                                                                          |
| -------------------------------------- | ----------------------------------------------------------------------------- |
| `.github/workflows/python-uv.yml`      | Reusable CI: uv sync, ruff, pyright, pytest (optional private sibling checkout) |
| `.github/workflows/java-gradle.yml`    | Reusable CI: Gradle build and tests                                           |
| `.github/pull_request_template.md`     | Default PR template for every repo in the org without its own                 |
| `.github/ISSUE_TEMPLATE/`              | Default issue forms (bug, feature)                                            |
| `SECURITY.md`                          | Default security policy                                                       |

## Using a workflow

```yaml
jobs:
  check:
    uses: ResoDesk/.github/.github/workflows/python-uv.yml@v1
```

Callers pin a major tag (`v1`). A breaking change gets a new major tag; non-breaking fixes move the existing tag
(`git tag -f v1 && git push -f origin v1`) after they pass in one caller.

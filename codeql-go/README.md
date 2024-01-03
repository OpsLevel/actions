# Uses CodeQL to analyze Go source code

This [composite action](https://docs.github.com/en/actions/creating-actions/about-custom-actions#composite-actions)
leverages Github's [codeql-action](https://github.com/github/codeql-action) to analyze Go source code based on the
Go version found in the calling repository's `go.mod` file. This allows us to update Go versions in our code
independently of the upstream `codeql-action`.

More details on CodeQL available in [their docs](https://codeql.github.com/docs/).

Example:

```yaml
name: Example Workflow for CodeQL analysis with latest Go version
on:
  push:
    branches:
      - main

jobs:
  test:
    name: test and analyze
    runs-on: ubuntu-latest
    steps:
      - name: checkout repo
        uses: actions/checkout@v4
        with:
          submodules: 'recursive'

      - name: CodeQL analyze with Go
        uses: opslevel/actions/codeql-go@main
        with:
          go_mod_path: src
```

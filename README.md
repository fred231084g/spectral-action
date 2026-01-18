# Spectral Linter Action

This action uses [Spectral](https://github.com/stoplightio/spectral) 
on:
  - pull_request

jobs:
  build:
    name: Run Spectral
    runs-on: ubuntu-latest
    steps:
      # Check out the repository
      - uses: actions/checkout@v3

      # Run Spectral
      - uses: stoplightio/spectral-action@latest
        with:
          file_glob: 'doc/api/*.yaml'
```

### Inputs

- **file_glob:** Pattern describing the set of files to lint. Defaults to `*.oas.{json,yml,yaml}`. (_Note:_ Pattern syntax is documented in the [fast-glob](https://www.npmjs.com/package/fast-glob) package documentation)
- **spectral_ruleset:** Custom ruleset to load in Spectral. When unspecified, will try to load the default `.spectral.yaml` ruleset if it 

# Rust Release Action

Automatically creates and publishes GitHub releases for Rust projects when `Cargo.toml` version is updated. Supports publishing to crates.io as well.

## Usage

Here is an example workflow that uses the `rust-release` action:
```yaml
name: Release
on:
  push:
    branches: [main]  # your main branch
    paths:
      - 'Cargo.toml'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - uses: jokelbaf/rust-release@master
```

## Acknowledgements

[Seria's](https://github.com/seriaati) [create-release](https://github.com/seriaati/create-release) action (for python) was used as a reference for rust-release.

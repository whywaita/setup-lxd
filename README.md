# setup-lxd

setup-lxd setup [LXD](https://linuxcontainers.org/lxd/) Server in GitHub Actions

## Usage

```
name: build

on:
  push:
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: whywaita/setup-lxd@v1
        with:
          lxd_version: latest/stable
      - name: Launch instance
        run: |
          lxc launch ubuntu:focal build-server
```

## Inputs

### `lxd_version`

- version of LXD.
- available version list is [snapcraft](https://snapcraft.io/lxd).
- default: `latest/stable`


# ☁️ XVFB Github Action

> _Forked from [`GabrielBB/xvfb-action`](https://github.com/GabrielBB/xvfb-action) and updated to Node v16.x_

This action installs [XVFB](http://elementalselenium.com/tips/38-headless) and runs your headless integration tests with it. It cleans up the xvfb process after your tests are done. If the action detects you're not using linux then your tests still run — just without xvfb — which is practical for multi-platform workflows.

### Example usage

```yml
on: [push]

jobs:
  build:
    strategy:
      matrix:
        os: [macos-latest, ubuntu-latest, windows-latest]
    runs-on: ${{ matrix.os }}

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Run integration tests
        uses: smithki/xvfb-action@v1.1.2
        with:
          run: npm test
          working-directory: ./ #optional
          options: #optional
```

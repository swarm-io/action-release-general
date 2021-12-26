<!-- start title -->
<!-- end title -->
<!-- start description -->
<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->
<!-- end usage -->
<!-- start inputs -->
<!-- end inputs -->
<!-- start outputs -->
<!-- end outputs -->
<!-- start examples -->
### Example usage
```yaml
name: Release
on:
  pull_request:
    types:
      - closed
    branches:
      - main
jobs:
  release:
    runs-on: ubuntu-latest
    name: Release
    steps:
      - uses: swarm-io/action-release-general@v1
        with:
          token: ${{ secrets.GIT_RUNNER_TOKEN }}
```
<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->

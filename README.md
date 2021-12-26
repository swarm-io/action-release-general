<!-- start title -->

# GitHub Action:General Release

<!-- end title -->
<!-- start description -->

A simple action that has an option to toggle `include administrators` on branch protection, and then run semantic-release with a given release config

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: swarm-io/action-release-general@undefined
  with:
    # git token to use for the run
    token: ""

    # If true, this action will disable the `include administrators` setting in branch
    # protection for this branch, and re-enable it after release. Re-enabling is run
    # using always()
    # Default: false
    toggle-admins: ""

    # The release configuration to use for the release. Set this to
    # `@swarm-io/release-config-javascript-actions` for javascript actions
    # Default: @swarm-io/release-config-general
    release-config: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**            | **Description**                                                                                                                                                                |            **Default**             | **Required** |
| :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------: | :----------: |
| **`token`**          | git token to use for the run                                                                                                                                                   |                                    |   **true**   |
| **`toggle-admins`**  | If true, this action will disable the `include administrators` setting in branch protection for this branch, and re-enable it after release. Re-enabling is run using always() |                                    |  **false**   |
| **`release-config`** | The release configuration to use for the release. Set this to `@swarm-io/release-config-javascript-actions` for javascript actions                                             | `@swarm-io/release-config-general` |  **false**   |

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

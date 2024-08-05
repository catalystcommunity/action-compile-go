<!-- start title -->

# GitHub Action:Compile Go

<!-- end title -->
<!-- start description -->

Compiles a golang project

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystcommunity/action-compile-go@undefined
  with:
    # Version of golang to use
    # Default: ~1.20
    go-version: ""

    # Directory to run the command from
    # Default: .
    working-directory: ""

    # Command to run
    # Default: go build -race ./...
    command: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**               | **Description**                   |      **Default**       | **Required** |
| :---------------------- | :-------------------------------- | :--------------------: | :----------: |
| **`go-version`**        | Version of golang to use          |        `~1.20`         |  **false**   |
| **`working-directory`** | Directory to run the command from |          `.`           |  **false**   |
| **`command`**           | Command to run                    | `go build -race ./...` |  **false**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
on:
  pull_request:
    branches:
      - main
jobs:
  ensure-compile:
    if: github.event.pull_request.draft == false
    name: Ensure project compiles
    runs-on: ubuntu-latest
    steps:
      - uses: crazy-max/ghaction-dump-context@v1
      - uses: catalystcommunity/action-compile-go@v1
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->

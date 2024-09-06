# Shared Workflows

See shared workflow **templates** here: 
https://github.com/lightzane/try-ghactions-sharedwf/tree/main/.github/workflows

See other / external workflows calling the shared workflows:
https://github.com/lightzane/try-ghactions-output/blob/main/.github/workflows/shared_workflow.yaml

```yaml
name: Shared Workflow

on: 
  push:
  workflow_dispatch:

jobs:
  test1:
    # your-org/repo/.github/workflows/wf-name.yaml@main
    uses: lightzane/try-ghactions-sharedwf/.github/workflows/shared.yaml@v1
    with:
      example_input: "Hello world!"

  test2:
    uses: lightzane/try-ghactions-sharedwf/.github/workflows/shared.yaml@dev
    with:
      example_input: "Hello DEV!"

  test3:
    uses: lightzane/try-ghactions-sharedwf/.github/workflows/shared-too.yaml@v3
    with:
      two: "Number two"

  test4:
    uses: lightzane/try-ghactions-sharedwf/.github/workflows/shared.yaml@v2
    with:
      example_input: "Version two"
```

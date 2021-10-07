# gh-actions-workflows

GitHub Workflows um sie in anderen Repositories zu verwenden

GitHub Dokumentation zu wiederverwendbaren Workflows: https://docs.github.com/en/actions/learn-github-actions/reusing-workflows

## Anwendungsbeispiele

z.B.: `on_pr.yml`:

```yml
name: On Pull-Request

# Controls when the action will run. 
on:

  pull_request:
    types: [ opened, edited, synchronize, reopened, ready_for_review, reopened ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  lint:
    uses: Weitkamper/gh-actions-workflows/.github/workflows/lint.yml@main
```

z.B.: `on_push-master.yml`:

```yml
name: On push in master

on:
  push:
    branches:
      - master

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

jobs:        
  draft_release:
    uses: Weitkamper/gh-actions-workflows/.github/workflows/draft_release.yml@main
```

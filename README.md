# Starter guide for new projects

## GitHub Actions

Create a `README.md` file with the next content:
``` markdown
<!-- START .github/README.template.md -->
<!-- END .github/README.template.md -->
```

Create a new file in `.github/workflows/update.yml`
``` yaml
name: Maintain

on:
  workflow_dispatch:
  schedule: [{ cron: "0 0 * * 0" }]

jobs:
  update:
    name: Maintain
    uses: luisfalconmx/.github/.github/workflows/update.yml@main
    secrets:
      PERSONAL_ACCESS_TOKEN: ${{ secrets.PERSONAL_ACCESS_TOKEN }}
```

Make sure to define the secret `PERSONAL_ACCESS_TOKEN` in your repository

Finally, you need to configure an action to make automatic records of the changes that may exist in the future

Then create a new file in `.github/release-drafter.yml`

``` yaml
_extends: .github
```

And create a new file in `.github/workflows/release.yml`

``` yaml
name: Release

on:
  push:
    branches:
      - main

jobs:
  update:
    name: Release
    uses: luisfalconmx/.github/.github/workflows/release.yml@main
```
# Starter guide for new projects

## GitHub Actions

Create a README file with the next content:
``` markdown
<!-- START .github/README.template.md -->
<!-- END .github/README.template.md -->
```

Create a new file in `.github/workflows/update.yml`
``` yaml
name: Update Repository

on:
  workflow_dispatch:
  schedule: [{ cron: "0 0 * * 0" }]

jobs:
  update:
    uses: luisfalconmx/.github/.github/workflows/update.yml@main
    secrets:
      PERSONAL_ACCESS_TOKEN: ${{ secrets.PERSONAL_ACCESS_TOKEN }}

```
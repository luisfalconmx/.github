# Starter guide for new projects

## GitHub Actions

Add `.github/workflows/analyze.yml` in your project

```yaml
name: Analyze

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
  schedule:
    - cron: "39 5 * * 0"

jobs:
  scan:
    name: Analyze
    uses: luisfalconmx/.github/.github/workflows/analyze.yml@main
    with:
      language: javascript
```

Create a `README.md` file with the next content:

```markdown
<!-- START .github/README_TEMPLATE/frontend.template.md -->
<!-- END .github/README_TEMPLATE/frontend.template.md -->
```

Create a new file in `.github/workflows/update.yml`

```yaml
name: Update

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

```yaml
_extends: .github
```

And create a new file in `.github/workflows/release.yml`

```yaml
name: Release

on:
  push:
    branches:
      - main

jobs:
  release:
    name: Release
    uses: luisfalconmx/.github/.github/workflows/release.yml@main
```

## Linters and more

See the following links to configure linters and project configurations:

- [https://github.com/okonet/lint-staged#examples](https://github.com/okonet/lint-staged#examples)
- [https://www.npmjs.com/package/husky](https://www.npmjs.com/package/husky)
- [https://github.com/conventional-changelog/commitlint#config](https://github.com/conventional-changelog/commitlint#config)
- [https://github.com/luisfalconmx/create-spa-app/blob/main/.husky/pre-commit](https://github.com/luisfalconmx/create-spa-app/blob/main/.husky/pre-commit)
- [https://github.com/luisfalconmx/instagram-clon](https://github.com/luisfalconmx/instagram-clon)

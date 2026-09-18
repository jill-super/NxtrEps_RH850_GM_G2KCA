---
title: "Deployment"
description: "How to publish this documentation site."
---
## Local preview

```sh
cd docs
npm install
npm run dev
```

## Static build

```sh
cd docs
npm install
npm run build
```

The static site is emitted to `docs/dist/`.

## Publishing without hardcoding the address

The site configuration derives its address automatically at build time from the git remote or from the standard continuous-integration variable, so forks need no edits. The snippet below is a minimal Pages workflow illustration kept here as documentation (no workflow files are shipped, so existing automation is left untouched):

```yaml
name: docs
on:
  push:
    branches: [main]
    paths: [docs/**]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
      - run: npm ci
        working-directory: docs
      - run: npm run build
        working-directory: docs
      - uses: actions/upload-pages-artifact@v3
        with:
          path: docs/dist
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deploy.outputs.page_url }}
    steps:
      - id: deploy
        uses: actions/deploy-pages@v4
```

Dependency updates and automatic merging are intentionally not configured here: automation files are left exactly as found.

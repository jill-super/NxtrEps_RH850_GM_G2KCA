# Documentation site source

This folder is the Astro project root for the documentation site.

- Content lives in `src/content/docs/` and is organised by AUTOSAR layer.
- Preview locally with `npm install` followed by `npm run dev`.
- Build with `npm run build`. The static site is emitted to `dist/`.
- Deployment is described in `src/content/docs/general/deployment.md`.
  The site address is derived automatically from the git remote, so forks need no configuration edits.

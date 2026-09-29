# packages (apt + dnf example)

Example GitHub Pages host for **apt** and **dnf** repositories, for use with
[foss-template](https://github.com/adamsiwiec1/foss-template).

## Why this repo exists

`apt` and `dnf` need an HTTP repository (package pool + metadata indexes). A
GitHub Release asset alone is not enough. This repo holds the published tree;
enable **Settings → Pages** (branch `gh-pages` or `main`).

Production reference: [openhat-security/packages](https://github.com/openhat-security/packages).

## Build

From your app repo after releasing `.deb` / `.rpm` files:

```bash
REPO_URL=https://adamsiwiec1.github.io/packages \
  ./packaging/repo/build-pages-repos.sh ./dist/linux-packages ./dist/pages
# push ./dist/pages → this repo (gh-pages)
```

Templates: [`foss-template/packaging/repo`](https://github.com/adamsiwiec1/foss-template/tree/main/packaging/repo).

## Users (once Pages is live)

```bash
curl -fsSL https://adamsiwiec1.github.io/packages/install-apt.sh | sudo bash
curl -fsSL https://adamsiwiec1.github.io/packages/install-dnf.sh | sudo bash
```

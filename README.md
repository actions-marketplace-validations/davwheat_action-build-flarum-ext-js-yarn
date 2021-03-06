# [GitHub Action] Flarum JavaScript Building

---

**This is a fork of the [official Flarum core action](https://github.com/flarum/action-build).** I personally prefer `yarn` over `npm`, so have modified the core action to suit those preferences.

---

This action automatically compiles & commits yours JavaScript extension files on every commit.

## Example Workflow

```yml
name: Flarum Build

on: push

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@master
      - uses: davwheat/action-build-flarum-ext-js-yarn@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Only Build on Master

If you only want to run the workflow when commits are pushed to the `master` branch, change `on: push` to the following:

```yml
on:
  push:
    branches:
      - master
```

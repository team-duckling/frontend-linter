
# Duckling Frontend Linters

## EsLint

TBD
## Prettier Lint

TBD
## Style Lint

TBD
## Commit Lint

<p align="center">
  <img width="600" src="docs/assets/commitlint.svg">
</p>

### What is commitlint

commitlint checks if your commit messages meet the [conventional commit format](https://conventionalcommits.org).

In general the pattern mostly looks like this:

```sh
type(scope?): subject  #scope is optional; multiple scopes are supported (current delimiter options: "/", "\" and ",")
```

Real world examples can look like this:

```
chore: run tests on travis ci
```

```
fix(server): send cors headers
```

```
feat(blog): add comment section
```

Common types according to [commitlint-config-conventional (based on the Angular convention)](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional#type-enum) can be:

- build
- chore
- ci
- docs
- feat
- fix
- perf
- refactor
- revert
- style
- test

These can be modified by [your own configuration](#config).

### Benefits using commitlint

- [Why Use Conventional Commits?](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#why-use-conventional-commits)
- ["The perks of committing with conventions" (Talk slides)](https://slides.com/marionebl/the-perks-of-committing-with-conventions#/)

## Husky

<p>Husky improves your commits and more 🐶 <em>woof!</em></p>
<p>You can use it to <strong>lint your commit messages</strong>, <strong>run tests</strong>, <strong>lint code</strong>, etc... when you commit or push. Husky supports <a href="https://git-scm.com/docs/githooks" target="_blank" rel="noreferrer">all Git hooks</a>.</p>
<p>Click <a href="/husky/getting-started.html">here</a> to get started.</p>

## Lint-Staged
Run linters against staged git files and don't let :poop: slip into your code base!

```bash
npm install --save-dev lint-staged # requires further setup
```

```
$ git commit

✔ Preparing lint-staged...
❯ Running tasks for staged files...
  ❯ packages/frontend/.lintstagedrc.json — 1 file
    ↓ *.js — no files [SKIPPED]
    ❯ *.{json,md} — 1 file
      ⠹ prettier --write
  ↓ packages/backend/.lintstagedrc.json — 2 files
    ❯ *.js — 2 files
      ⠼ eslint --fix
    ↓ *.{json,md} — no files [SKIPPED]
◼ Applying modifications from tasks...
◼ Cleaning up temporary files...
```

## Why

Linting makes more sense when run before committing your code. By doing so you can ensure no errors go into the repository and enforce code style. But running a lint process on a whole project is slow, and linting results can be irrelevant. Ultimately you only want to lint files that will be committed.

This project contains a script that will run arbitrary shell tasks with a list of staged files as an argument, filtered by a specified glob pattern.


## Referrences

[0]: https://eslint.org/docs/latest/use/getting-started
[1]: https://prettier.io/docs/en/install
[2]: https://github.com/primer/stylelint-configs
[3]: https://stylelint.io/user-guide/get-started
[4]: https://www.npmjs.com/package/husky
[5]: https://www.npmjs.com/package/lint-staged
[6]: https://github.com/conventional-changelog/commitlint

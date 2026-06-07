# Repository Template

[![Continuous integration](https://github.com/stairwaytowonderland/repository-template/actions/workflows/ci.yaml/badge.svg)](https://github.com/stairwaytowonderland/repository-template/actions/workflows/ci.yaml)
[![GitHub latest release](https://img.shields.io/github/v/release/stairwaytowonderland/repository-template?include_prereleases&logo=rocket)](https://github.com/stairwaytowonderland/repository-template/releases)
[![GitHub last commit](https://img.shields.io/github/last-commit/stairwaytowonderland/repository-template/main?logo=git)](https://github.com/stairwaytowonderland/repository-template/commits/main)
[![GitHub license](https://img.shields.io/github/license/stairwaytowonderland/repository-template?logo=opensourceinitiative&labelCol&color=yellow&logoColor=white)](https://github.com/stairwaytowonderland/repository-template/tree/main/LICENSE)
[![semantic-release: conventionalcommits](https://img.shields.io/badge/semantic--release-cc-FE5196?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
[![pre-commit](https://img.shields.io/badge/pre--commit-FAB040?logo=pre-commit&logoColor=black)](https://github.com/pre-commit/pre-commit)

A minimal starting point for a basic repository. :surfer: :rocket: :flying_saucer: :milky_way: :monkey:

## Project structure

> [!NOTE]
> `tree -a -F -L 3 -I '.git|.vscode' --gitignore --dirsfirst .`

```none
./
├── .github/
│   ├── workflows/
│   │   ├── ci.yaml
│   │   ├── conventional-commit.yaml
│   │   ├── create-labels.yaml
│   │   ├── import-csv-issues.yaml
│   │   ├── pre-commit.yaml
│   │   ├── publish.yaml
│   │   └── release.yaml
│   └── dependabot.yml
├── .editorconfig
├── .gitignore
├── .markdownlint.json
├── .pre-commit-config.yaml
├── .prettierignore
├── .prettierrc
├── LICENSE
├── README.md
└── TODO.sample.csv
```

## Getting started

### Option 1: Use this template

1. Click the **Use this template** button at the top of the repository
1. Select **Create a new repository**
1. Select an owner and name for your new repository
1. Click **Create repository**
1. Clone your new repository

> [!IMPORTANT]
>
> Make sure to  update the [`README.md`](./README.md) _(this file)_ and [`LICENSE`](./LICENSE) files accordingly.

### Option 2: Clone this repo

```bash
git clone git@github.com:stairwaytowonderland/repository-template.git
```

#### Create a new repository from the command line

```bash
# Delete the .git folder from cloned project
rm -rf .git

# Overwrite README with your content
echo "# my-fun-project" >> README.md

# Initialize new git local repository
git init

# Set default branch
git branch -M main

# Make first commit empty to allow easier rebasing
git commit --no-verify --allow-empty -m "chore: initial empty commit"

# Install pre-commit hooks
# (make sure `pre-commit` is installed ... install it using `pip` or `brew`)
pre-commit install

# Add all files (make sure your .gitignore file is properly configured)
git add .

# Second commit
git commit -m "chore: adding initial files"

# Set remote ...
# To update the url (instead of add), use `git remote set-url origin <GIT_URL>`
git remote add origin git@github.com:<user-or-org>/<new-existing-repo>.git

# Push to remote
git push -u origin main
```

## Commit Message Guidelines

- Write clear, concise commit messages that follow the
  [![conventional-commit](https://img.shields.io/badge/conventional--commit-FE5196?logo=conventionalcommits&logoColor=white)](https://www.conventionalcommits.org/)&nbsp;standard.
- The allowed tags for this project are the following:

```json
[
  "build",
  "chore",
  "ci",
  "docs",
  "feat",
  "fix",
  "perf",
  "refactor",
  "revert",
  "style",
  "test"
]
```

> [!NOTE]
>
> See [Contributing Guidelines](https://github.com/stairwaytowonderland/.github/blog/main/CONTRIBUTING.md) for more information.

## Releasing

This project uses **`semantic-release`** with the _conventionalcommits_ preset by default, as well as _default_
[`package.json`](https://github.com/stairwaytowonderland/node-semantic-release/blob/main/templates/package.json)
and [`.releaserc`](https://github.com/stairwaytowonderland/node-semantic-release/blob/main/templates/releaserc.json) files.

**The creation of tags and releases is handled _automatically_ by the pre-configured workflows.**

> [!TIP]
>
> In most cases, only the `.releaserc` needs to by _copied/customized_.

## Further customizations

### Contributing details

For customized **contributing details**, create a `CONTRIBUTING.md` in this repo:

```bash
echo "# Contributing Guidelines" > CONTRIBUTING.md
```

> [!TIP]
>
> You may copy the organization [`CONTRIBUTING.md`](https://github.com/stairwaytowonderland/.github/blob/main/CONTRIBUTING.md)
> file as a starting point.

### Issues and PRs

For simplicity reasons, this template repo doesn't include the `ISSUE_TEMPLATE` and `PULL_REQUEST_TEMPLATE` _(.md)_
files.

> [!TIP]
>
> If **_using this template in another org_, or to _add those files to your project for futher customization_**, copy
> them from this organization's [_special .github repo_](https://github.com/stairwaytowonderland/.github/tree/main/.github).

## Essential tools

- [Visual Studio Code](https://code.visualstudio.com/) (a.k.a. _VS Code_)
- [EditorConfig](https://editorconfig.org/)
- [pre-commit](https://pre-commit.com/)
- [Prettier](https://prettier.io/)
  > **Note:** For a more customized experience, some files might need to be excluded from _Prettier_.
  >
  > See the [official docs](https://prettier.io/docs/ignore) for details on ignoring code.

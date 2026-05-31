# Repository Template

A minimal starting point for a basic repository.

## Project structure

> [!NOTE]
> `tree -a -F -L 3 -I '.git|.vscode' --gitignore --dirsfirst .`

```none
./
├── .github/
│   ├── workflows/
│   │   ├── ci.yaml
│   │   ├── conventional-commit.yaml
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
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── TODO.sample.csv
```

## Using this template

Update the [`README.md`](./README.md) (this file), [`CONTRIBUTING.md`](./CONTRIBUTING.md), and [`LICENSE`](./LICENSE)
files accordingly, and change any placeholders to suit your needs (e.g. the `[Organization Name]` and `[Repository Name]`
placeholders in *CONTRIBUTING.md*).

## Issues and PRs

For simplicity reasons, this template repo doesn't include the `ISSUE_TEMPLATE` and `PULL_REQUEST_TEMPLATE` *(.md)* files.

To add those to your project, copy this organization's global defaults from the
[**.github**](https://github.com/stairwaytowonderland/.github/tree/main/.github) *special* repo.

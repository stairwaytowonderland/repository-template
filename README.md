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
├── LICENSE
├── README.md
└── TODO.sample.csv
```

## Getting Started

### Clone this Repo

```bash
git clone git@github.com:stairwaytowonderland/repository-template.git
```

### Create a new repository from the command line

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
git commit -m "chore: Adding initial files"

# Set remote ...
# To update the url (instead of add), use `git remote set-url origin <GIT_URL>`
git remote add origin git@github.com:<user-or-org>/<new-existing-repo>.git

# Push to remote
git push -u origin main
```

## Essential Tools

- [Visual Studio Code](https://code.visualstudio.com/) (a.k.a. _VS Code_)
- [EditorConfig](https://editorconfig.org/)
- [Prettier](https://prettier.io/)
- [pre-commit](https://pre-commit.com/)

> [!NOTE]
> For a more customized experience, some files might need to be excluded from _Prettier_.
>
> See the [official docs](https://prettier.io/docs/ignore) for details on ignoring code.

## Using this template

Update the [`README.md`](./README.md) _(this file)_ and [`LICENSE`](./LICENSE) files accordingly.

### Further customizations

- **`CONTRIBUTING.md`:** For customized **contributing details**, copy the organization [`CONTRIBUTING.md`](./CONTRIBUTING.md)
file as a starting point.

> [!TIP]
>
> ### Issues and PRs
>
> For simplicity reasons, this template repo doesn't include the `ISSUE_TEMPLATE` and `PULL_REQUEST_TEMPLATE` _(.md)_ files.
>
> If **_using this template in another org_, or to _add those files to your project for futher customization_**,
> copy them from this organization's _special_
> [**.github**](https://github.com/stairwaytowonderland/.github/tree/main/.github) repo.

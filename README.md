# Repository Template

A minimal starting point for a basic repository.

## Project structure

> [!NOTE]
> `tree -a -F -L 2 -I '.git|.vscode' --gitignore --dirsfirst .`

```none
./
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── workflows/
│   ├── dependabot.yml
│   └── PULL_REQUEST_TEMPLATE.md
├── .editorconfig
├── .gitignore
├── .markdownlint.json
├── .pre-commit-config.yaml
├── .prettierignore
├── .prettierrc
├── .releaserc
├── CONTRIBUTING.md
├── LICENSE
├── package-lock.json
├── package.json
└── README.md
```

## Enabling Changelog Generation (for downstream repos)

This template disables changelog generation by default.

To enable changelog generation in your repository:

1. Add the `@semantic-release/changelog` plugin to `.releaserc`:

    ```json
    {
      // ...
      plugins: [
        // [...],
        [
          "@semantic-release/changelog",
          {
            "changelogFile": "CHANGELOG.md"
          }
        ],
        // [...]
      ]
    }
    ```

2. Install the dependency:

    ```sh
    npm install --save-dev @semantic-release/changelog
    ```

3. Commit your changes.

This will allow semantic-release to generate and update `CHANGELOG.md` on each release.

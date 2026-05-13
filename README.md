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

This template disables changelog generation and asset modification by default.

1. ### Enable changelog generation in your repository

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

2. ### Enable asset modification in your repository

   1. Update the `@semantic-release/git` plugin in `.releaserc`:

       ```json
       {
         // ...
         plugins: [
           [
             // [...],
             "@semantic-release/git",
             {
               "assets": [
                 "CHANGELOG.md",
                 "package.json",
                 "package-lock.json"
               ],
               "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}"
             },
             // [...]
           ]
         ]
       }
       ```

3. ### Commit your changes

    This will allow:

    - **semantic-release** to generate and update `CHANGELOG.md` on each release
    - **semantic-release** to update the main version in `package.json` and `package-lock.json` on each release

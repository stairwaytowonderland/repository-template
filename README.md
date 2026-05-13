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

## Enabling Changelog Generation and Asset Modifications

To **generate a Changelog** and allow `git` to update the modified assets during a release, the appropriate `changelog`
and `git` plugins must
be installed and/or configured.

1. ### Configure the plugins

     1. Add the `@semantic-release/changelog` and `@semantic-release/changelog` plugins to `.releaserc`:

         ```json
         {
           "plugins": [
             [
               "@semantic-release/changelog",
               {
                 "changelogFile": "CHANGELOG.md"
               }
             ],
             [
               "@semantic-release/git",
               {
                 "assets": [
                   "CHANGELOG.md",
                   "package.json",
                   "package-lock.json"
                 ],
                 "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}"
               }
             ]
           ]
         }
         ```

     2. Install the `@semantic-release/changelog` and `@semantic-release/git` npm dependencies:

         ```sh
         npm install --save-dev @semantic-release/changelog
         npm install --save-dev @semantic-release/git
          ```

1. ### Commit your changes

    This will allow:

    - **semantic-release** to generate and update `CHANGELOG.md` on each release
    - **semantic-release** to update the main version in `package.json` and `package-lock.json` on each release

> [!TIP]
>
> ## Alternative approach
>
> Even though it's typical to modify `CHANGELOG.md` and `package.json` during the release, **generating the *Changelog*
> and uploading it as an artifact** (without modifying `package.json`) is an alternative approach that could
> *avoid any asset modifications* during a release.
>
> If using the alternative approach, only the `changelog` plugin needs to be installed/configured.

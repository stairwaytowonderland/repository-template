# The `.github` Directory

## :cactus: File Structure

> [!NOTE]
>
> `tree -a -F -L 3 -I --gitignore --dirsfirst .`

```none
.github/
├── workflows/
│   ├── ci.yaml
│   ├── conventional-commit.yaml
│   ├── create-labels.yaml
│   ├── dependabot-tests.yaml
│   ├── import-csv-issues.yaml
│   ├── pre-commit.yaml
│   ├── publish.yaml
│   ├── release.yaml
│   ├── repository-created.yaml
│   ├── watchers.yaml
│   └── watchers.yaml.bak
├── CODEOWNERS
├── dependabot.yml
└── README.md
```

> [!TIP]
>
> If a repository contains more than one _README_ file, then the file shown is chosen from locations in the following
> order: the **`.github`** directory, then the repository's **`root`** directory, and finally the **`docs`** directory.
>
> See the [**official docs**](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
> for more details.

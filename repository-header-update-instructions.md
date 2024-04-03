# Repository header update process:
- Clone the repository.
- Create a new branch called repository-header-update.
- Add file header.md to folder .config/
- Enable the header function in terraform-docs by adding the following three lines to file .terraform-docs.yml
```
header-from: ./.config/header.md

content: |-
 {{ .Header }}

sections:
  show:
    - header
```
- Execute the pre-commit, which executes terraform-docs v0.17.0, to update the README.md file at the repository's root.
```bash
alias pre-commit-run="curl -s -o '.pre-commit-config.yaml' https://raw.githubusercontent.com/StratusGrid/workflow-config/main/precommit-config/.pre-commit-config.yaml --next -o '.prettierignore' https://raw.githubusercontent.com/StratusGrid/workflow-config/main/precommit-config/.prettierignore && pre-commit run -a ; rm '.pre-commit-config.yaml' '.prettierignore'"
```
```bash
pre-commit-run
```
- Push the branch with changes to GitHub and create the PR. Add reviewers.
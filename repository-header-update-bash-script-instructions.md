Execute the folowing commands in the terminal (macOS) Github folder:

eval "$(ssh-agent -s)"

ssh-add --apple-use-keychain ~/.ssh/GITHUB_PRIVATE_HUB

git clone git@github.com:StratusGrid/REPOSITORY_NAME.git

cd REPOSITORY_NAME

git branch repository-header-update

git checkout repository-header-update

```
touch .config/header.md && echo '<p align="center">                                                                                                                                            
                                                                                
  <img src="https://github.com/StratusGrid/terraform-readme-template/blob/main/header/stratusgrid-logo-smaller.jpg?raw=true" />
  
  <p align="center">
    <a href="https://stratusgrid.com/book-a-consultation">Contact Us Test</a>
    <a href="https://stratusgrid.com/cloud-cost-optimization-dashboard">Stratusphere FinOps</a>
    <a href="https://stratusgrid.com">StratusGrid Home</a>
    <a href="https://stratusgrid.com/blog">Blog</a>
  </p>
</p>' >> .config/header.md
```
```
sed -i '' '1i\'$'\n''header-from: ./.config/header.md\'$'\n\n' .config/.terraform-docs.yml
```
```
sed -i '' -e '/content:/a\'$'\n''\ {{ .Header }}\'$'\n' .config/.terraform-docs.yml
```
```
sed -i '' -e '/show:/a\'$'\n''\ \ \ \ - header' .config/.terraform-docs.yml
```
```
# PRECOMMIT CONFIG
export PRECOMMIT_BRANCH="main"
alias pre-commit-run="curl -s -o '.pre-commit-config.yaml' https://raw.githubusercontent.com/StratusGrid/workflow-config/$PRECOMMIT_BRANCH/precommit-config/.pre-commit-config.yaml --next -o '.prettierignore' https://raw.githubusercontent.com/StratusGrid/workflow-config/$PRECOMMIT_BRANCH/precommit-config/.prettierignore --next -o '.tflint.hcl' https://raw.githubusercontent.com/StratusGrid/workflow-config/$PRECOMMIT_BRANCH/precommit-config/.tflint.hcl && pre-commit run -a ; rm '.pre-commit-config.yaml' '.prettierignore' '.tflint.hcl' ; rm -rf '.pre-commit-trivy-cache'"
```
pre-commit-run

pre-commit-run

git add .

git commit -m "repository-header-update"

git push --set-upstream origin repository-header-update

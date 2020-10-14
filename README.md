# Command-Archive

## git
`git reset HEAD~1 --soft`

### Change a Git commit message after a push
Use this [link](https://www.educative.io/edpresso/how-to-change-a-git-commit-message-after-a-push)

Unlike --force, which will destroy any changes someone else has pushed to the branch, --force-with-lease will abort if there was an upstream change to the repository.
```
git commit --amend -m "New message"

git push --force repository-name branch-name

git push --force-with-lease repository-name branch-name
```

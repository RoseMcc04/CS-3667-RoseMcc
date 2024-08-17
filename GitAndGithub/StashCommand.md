# Stash Command in Git

- Sometimes, programmers have changes that they have made, but they are not ready to commit them to the Git log. This could be due to branch switching, revert back temporarily to the origin, or you do not know what to do with your changes.
```shell
# Using spef-branch to demonstrate concept/example
git branch <spef-branch>
# Move to exaple branch
git checkout <spef-branch>
# Show changes
git diff
git stash save "message to remind you what stash is doing"
```  
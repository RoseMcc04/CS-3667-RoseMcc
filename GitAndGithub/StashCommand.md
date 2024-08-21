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
# Nothing to commit
git status
```
- We can show that there is something to not stash anymore with the following command
```shell
# Shows all stashes in the branch/repository
git stash -list
```

- Even though stashing is cool, we still need to eventually make these changes to the repository. We need to log them and then push them. 
```shell
# Will put changes back in staging area, but will not get rid of
# stash
git stash apply <stash-code>
# Grabs first stash in the list, applies changes to staging area, 
# and then drops the stash
git stash pop
```

- We can also save a specific change as a stash. 
```shell
git stash save "change message"
```
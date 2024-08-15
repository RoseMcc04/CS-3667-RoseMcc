# Common Mistakes in Git

- The idea is to look at how to fix mistakes in version control with Git commands, along with how it affects the commit history in the repository. 

## Context

- We can use ```git status``` to check which files we need to commit and which files have already been logged. 
- We can use ```git log``` to see the history of commits that have happened recently. 
- We can use ```git branch``` to see which branch we are actually on in the repository. 

## Reverting to Older Version

- We can checkout the file and that will reverse the changes. 
```shell
git checkout <file-name>
```
## Messing up a Commit Message

- As programmers, we tend to make mistakes when writing code and text, thus the concept of messing up a commit message is not compltely foreign.
```shell
git commit -m "<wrong-message>"
git commit --amend -m "<right-message>"
```

## Accidentally Leaving Off a File

- Sometimes, we forget to include a file or files in a commit. We will use a .gitignore as an example. We only do this if we have not pushed changes to other people. 
```shell
touch .gitignore
git add .gitignore
git commit --amend
# Log command to show more specific changes
git log --stat
```

## Committing to the Wrong Branch

- Branching can be tricky at first and beginners often make mistakes. The following lines will allow us to switch changes to other branches.
```shell
# Used to determine which hashcode to cherrypick. 
git log
git checkout <perferred-branch>
# Checking commit history of the preferred branch
git log
git cherry-pick <6-7 length of hashCode identity>
# Show that commits have switched
git log
```

## Resetting Commits

- There are a few ways of resetting commits in Git. 

### Resetting Commits - Soft

### Resetting Commits - Hard

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
git cherry-pick <6-7 length of hash from original>
# Show that commits have switched
git log
```

## Resetting Commits

- There are a few ways of resetting commits in Git. 

### Resetting Commits - Soft
```shell
git reset --soft <6-7 length of hash from original>
# Files will be shown in staging area
git status
```

### Resetting Commits - Mixed

```shell
git reset <6-7 length of hash from original>
# The commit history (log) will be modified
git log
# Changes are not in the staging area, they are in the working
# directory. 
git status
```

### Resetting Commits - Hard

```shell
git reset --hard <6-7 length of hash from original>
# The commit history (log) will be modified
git log
# Reverts all tracked files back to staging area, leaves untracked
# alone.
git status 
```

## Getting Rid of Untracked Files

We can get rid of untracked files to ease the process by ```git clean -df```. The 'd' stands for directories and the 'f' stands for files. 
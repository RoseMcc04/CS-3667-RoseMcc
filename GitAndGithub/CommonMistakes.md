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

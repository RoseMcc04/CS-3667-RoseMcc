# Git and GitHub Fundamentals Notes

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Help](#getting-help)
3. [Initialization and Committing](#initialization-and-committing)
4. [Stages: Working Directory, Staging Area, and .git directory (Repository)](#stages-working-directory-staging-area-and-git-directory-repository)

## Introduction

- Git is a distributed version control system, which means that   multiple machines can hold a local repository of the same project or server
- Centralized version control can only be used in one place, which can make collaboration difficult
- Git version:
```shell
git --version
```
- Setting up username:
```shell
git config --global user.name "<user-name>"
```
- Setting up email:
```shell
git config --global user.email "<user-email>"
```
## Getting Help

```shell
git help <keyword>
```
```shell
git <keyword> --help
```
## Initialization and Committing

- To initialize a git repository from existing code, we can traverse into a directory and type the following command
```shell
git init
```
- To ignore certain files in git, we can type ```touch .gitignore``` which creates a .gitignore file. This type of file allows us to add files for git to ignore.

## Stages: Working Directory, Staging Area, and .git directory (Repository)

- Staging area allows us to pick and choose which files we want committed
```shell
git add.gitignore
```
Individually adds .gitignore file to the staging area, but can also be done with general files as well
```shell
git reset
``` 
Will allow us to take a file out of the staging area

- Committing a file
```shell
git commit -m "specific message for file/code changes"
```
- Cloning a remote repository
```shell
git clone <url> <where to clone>
```
- Viewing information about the remote repository
```shell
git remove -v
git branch -a
```
- Pushing changes
```shell
git diff
git pull origin master
git push origin master
```
- Common workflow
    - Create a branch for a desired feature
    ```shell
    git branch <branch-name>
    git checkout <branch-name>
    ```
    - Do normal adding and staging/committing
    - Push branch changes to repository
    ```shell
    git push -u origin <branch-name>
    ```
- Merging a branch
```shell
git checkout master
git pull origin master
git branch --merged
git merge <branch-name>
git push origin master
```
- Deleting a branch
```shell
git branch --merged
git branch -d <branch-name>
git branch -a
git push origin --delete <branch-name>
```

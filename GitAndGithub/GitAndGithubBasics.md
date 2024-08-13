# Git and GitHub Fundamentals Notes

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


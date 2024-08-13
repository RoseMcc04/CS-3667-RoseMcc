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
- To ignore certain files in git, we can type ```shelltouch .gitignore``` which creates a .gitignore file. This type of file allows us to add files for git to ignore. 

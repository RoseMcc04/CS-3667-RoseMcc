# Intermediate Git and Github

## Table of Contents

1. [Proper Way to Create a Pull Request](#Proper-Way-to-Create-a-Pull-Request)
2. [How to Fix Conflicts](#How-to-Fix-Conflicts)
3. [Rebase vs. Merge](#Rebase-vs.-Merge)
4. [Modifying Existing Remote Branches](#Modifying-Existing-Remote-Branches)
5. [Cherry Pick and Reset](#Cherry-Pick-and-Reset)

### Proper Way to Create a Pull Request

With a team or a group of developers, you create a pull request to allow the user the request is for to revise their code and then push said code back into the repository. 

Only the admin of the repository is allowed to push changes to main or master, which means that you have to push changes to a branch, allow the admin to create a pull request if necessary, and then merge the changes once everything is finalized. 

Step 1: See which branch you are on. If you are not on the desired branch, switch to that branch. Make sure that the local repository is up to date with ```git pull``` or ```git pull <branch-name>```. 
```shell
git branch
git pull
git checkout -b <branch-name>
```

Step 2: Create the desired feature or file and start the process of pushing the file with changes to teh repository. 
```
git add <file-name>
git commit -m "commit message"
git push origin <branch-name>
```

### How to Fix Conflicts



### Rebase vs. Merge



### Modifying Existing Remote Branches



### Cherry Pick and Reset
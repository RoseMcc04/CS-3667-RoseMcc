# Intermediate Git and Github

## Table of Contents

1. [Proper Way to Create a Pull Request](#Proper-Way-to-Create-a-Pull-Request)
2. [How to Fix Conflicts](#How-to-Fix-Conflicts)
3. [Rebase vs. Merge](#Rebase-vs.-Merge)
4. [Modifying Existing Remote Branches](#Modifying-Existing-Remote-Branches)
5. [Cherry Pick and Reset](#Cherry-Pick-and-Reset)

## Proper Way to Create a Pull Request

With a team or a group of developers, you create a pull request to allow the user the request is for to revise their code and then push said code back into the repository. 

Only the admin of the repository is allowed to push changes to main or master, which means that you have to push changes to a branch, allow the admin to create a pull request if necessary, and then merge the changes once everything is finalized. 

Step 1: See which branch you are on. If you are not on the desired branch, switch to that branch. Make sure that the local repository is up to date with ```git pull``` or ```git pull <branch-name>```. 
```shell
git branch
git pull
git checkout -b <branch-name>
```

Step 2: Create the desired feature or file and start the process of pushing the file with changes to the repository. 
```
git add <file-name>
git commit -m "commit message"
git push origin <branch-name>
```

Step 3: The admin can click onto your branch on Github and creates a pull request. 

Step 4: The user the pull request is for will click a button called "Compare & pull request". The user will either have to upload a picture or two or input code changes or explain the reasoning for certain changes. 

Step 5: The admin will review the reasoning inputted to the pull request and determine if they will merge the pull request into the main/master branch or not. Sometimes, admin will request other uses or admin to review the pull request. 

## How to Fix Conflicts

1. Why do conflicts occur?

    - Conflicts can occur from the deletion of branches, a branch being behind main, or a multitude of other situations. 

2. How can we fix conflicts?

    - We can update the new branch used in the conflict to the main branch. 
    ```shell
    git checkout <main/master>
    git pull <main/master>
    git checkout <involved-branch>
    # If updated with repository
    git merge main
    # If not updated with repository
    git merge origin/main
    ```

## Rebase vs. Merge



## Modifying Existing Remote Branches



## Cherry Pick and Reset
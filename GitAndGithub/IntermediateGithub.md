# Intermediate Git and Github

Video: [Intermediate Git and Github](https://youtu.be/7h6_aZZ_iNg) 

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

In Git, a programmer can often run into scenarios where they need to integrate changes from one branch into another. Two common techniques are ```git merge``` and ```git rebase```. They work differently, but allow for ease of workflow. 

Git Merge:

- Combines changes from one branch to another branch
- Creates a new commit (merge commit) that ties the two branches together, preserving the history of both branches

```shell
git checkout main
git merge feature
```

```css
         A---B---C feature
        /         \
D---E---F---G------H main (merge commit)
```

- After merging, the history is kept and shows where the two branches diverged and where they merged

Git Rebase:

- Moves or combines a sequence of commits to a new base commit
- Rewrites history by applying changes on top of another branch, creating a linear history

```shell
git checkout feature
git rebase main
# If there are any conflicts, the process will pause and allow for resolve manually. You can continue now. 
git rebase --continue
```

```mathematica
Before Rebase:
D---E---F main
         \
          A---B---C feature

After Rebase:
D---E---F---A'---B'---C' feature
```

- After rebasing, the feature branch now appears as it was developed from the main branch without any divergence

![Rebase vs. Merge Diagram](https://miro.medium.com/v2/resize:fit:1400/1*mQOZjM3wwL1UV-ydQYAJTg.png)

## Modifying Existing Remote Branches

1. Renaming a Branch
```shell
# Locally
git branch -m <new-branch-name>
# Or rename another branch
git branch -m <old-branch-name> <new-branch-name>
# Push renamed branch to Github
git push origin <new-branch-name>
git push origin --delete <old-branch-name>
``` 

2. Deleting a Branch
```shell
git branch -d <branch-name>
# Force delete if branch has not been merged
git branch -D <branch-name>
# Delete a branch from Github
git push origin --delete <branch-name>
```

3. Rebasing a Branch
```shell
git checkout <specific-branch>
git rebase main
# If there are conflicts - Resolve conflicts
git rebase --continue
# Force push since repository was rewritten
git push origin <specific-branch> --force
```

4. Force-Pushing Changes
```shell
git push origin <branch-name> --force
```

5. Resetting a Branch to a Specific Commit
```shell
# Reset branch to a specific commit
git reset --hard commit-sha
# Force push the reset branch to Github
git push origin <branch-name> --force
```

6. Reverting Changes on a Branch
```shell
# Revert a specific commit
git revert commit-sha
# Push the revert commit to Github
git push origin <branch-name>
```
# Git Workflow Guide

## **1. Initializing a Git Repository**

First, create a folder in your local storage, navigate inside it, and initialize it as a Git repository:

```sh
git init
```

## **2. Staging and Committing Changes**

After making changes, stage them:

```sh
git add .
```

To stage changes interactively:

```sh
git add -p
```

Then commit the changes with a message:

```sh
git commit -m "write message"
```

To log all the changes:

```sh
git log
```

To search for specific commits containing a keyword:

```sh
git log --all --grep "something added"
```

Example output:

```
Author: Mahendra <mahendrakumar27697@gmail.com>
Date:   Wed Mar 5 12:39:52 2025 +0530

    added 2 files in master branch
```

## **3. Viewing Commit Details**

To show details of a specific commit:

```sh
git show 2aafad9df53e96fc8fcdde39ec9006c4f2fb52d7
```

To check the difference between the working directory and the last commit:

```sh
git diff HEAD
```

To check the difference between staged changes and the last commit:

```sh
git diff --staged
```

## **4. Comparing Branches**

To compare differences between two branches:

```sh
git log main..master
```

## **5. Stashing Changes**

If you want to temporarily save changes without committing:

```sh
git stash
```

To retrieve stashed changes:

```sh
git stash pop
```

To clear all stashed changes:

```sh
git stash clear
```

## **6. Resetting Changes**  

If you want to reset your repository to a specific commit, use the commit hash:  

```sh
git reset f96a0c38203e0987b24dcdc6b7b659b2919b7095
```  

To discard all local changes and reset to the last commit:

```sh
git reset --hard HEAD
```

## **7. Pushing to a Remote Repository**

To publish your local repository to GitHub:

1. Create a repository on GitHub and copy the repository link.
2. Add the remote repository:

```sh
git remote add origin git_repository_url
```

To check all remote URLs linked to your local repository:

```sh
git remote -v
```

To push all committed changes to the remote repository:

```sh
git push origin main
```

To delete a branch from the remote repository:

```sh
git push origin --delete master
```

or

```sh
git push origin:master
```

## **8. Renaming a Remote Repository**

To rename a remote repository from 'origin' to 'destination':

```sh
git remote rename origin destination
```

To change the remote repository URL:

```sh
git remote set-url origin new_repository_url
```

## **9. Branching in Git**

To create a new branch:

```sh
git branch branch_name
```

To list all branches:

```sh
git branch
```

To switch to another branch:

```sh
git checkout branch_name
```

To delete a local branch:

```sh
git branch -d branch_name
```

## **10. Forking and Contributing to Another Repository**

If you want to contribute to a project but lack direct permissions:

1. Fork the repository.
2. Add the upstream repository:

```sh
git remote add upstream repository_url_of_the_Project
```

To verify the remote repositories:

```sh
git remote -v
```

After making changes, push your branch and create a pull request on GitHub.

## **11. Syncing Forked Repository with Upstream**

If the upstream repository has updates that your forked repository lacks:

1. Switch to the main branch:

```sh
git checkout main
```

2. Fetch all logs:

```sh
git fetch --all --prune
```

3. Reset your branch to match upstream:

```sh
git reset --hard upstream/main
```

4. Push the updated upstream changes to your local main branch:

```sh
git push origin main
```

Alternatively, you can achieve all these steps with:

```sh
git pull upstream main
```

Then sync the changes with your local repository:

```sh
git push origin main
```

## **12. Viewing Short Log Summary**

To view a summary of commits by author:

```sh
git shortlog
```

## **13. Squashing Multiple Commits into One**

If multiple commits have been made, but you want to count them as one, you can use `pick` and `squash`:

1. Select the commit hash below all the commits you want to squash:

```sh
git rebase commit_hashcode
```

2. Mark the first commit as `pick` and all others as `s` (squash).
3. Write a commit message.
4. Exit using:

```
esc :x enter
```


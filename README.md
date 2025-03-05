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

Then commit the changes with a message:

```sh
git commit -m "write message"
```

To log all the changes:

```sh
git log
```

Example output:

```
Author: Mahendra <mahendrakumar27697@gmail.com>
Date:   Wed Mar 5 12:39:52 2025 +0530

    added 2 file in master branch

commit 8ec225f2e8e673e8d5cd0a772f2b2ccb0cca80e2
Author: Mahendra <mahendrakumar27697@gmail.com>
Date:   Wed Mar 5 12:24:34 2025 +0530

    conflict resolved
```

## **3. Stashing Changes**

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

## **4. Resetting Changes**  

If you want to reset your repository to a specific commit, use the commit hash:  

```sh
git reset f96a0c38203e0987b24dcdc6b7b659b2919b7095
```  
then 

```sh
git add .
```

then 
```sh
git stash
```
This command will reset all changes after the provided commit hash.  

---

## **5. Pushing to a Remote Repository**

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

## **6. Branching in Git**

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

## **7. Forking and Contributing to Another Repository**

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

## **8. Syncing Forked Repository with Upstream**

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

## **9. Squashing Multiple Commits into One**

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


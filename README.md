
# **Git Workflow Guide**  

## **1. Initialize a Git Repository**  
First, create a folder in your local storage and navigate inside it. Then, initialize the folder as a Git repository:  

```sh
git init
```  

Now you can start working on your project.  

---

## **2. Staging and Committing Changes**  

### **Stage all changes**  
```sh
git add .
```  

### **Commit the changes**  
```sh
git commit -m "Your commit message"
```  

---

## **3. View Commit History**  

To log all the changes made in the repository, use:  

```sh
git log
```  

Example output:  

```
Author: Mahendra <mahendrakumar27697@gmail.com>
Date:   Wed Mar 5 12:39:52 2025 +0530

    added 2 files in master branch

commit 8ec225f2e8e673e8d5cd0a772f2b2ccb0cca80e2
Author: Mahendra <mahendrakumar27697@gmail.com>
Date:   Wed Mar 5 12:24:34 2025 +0530

    conflict resolved
```

---

## **4. Resetting Changes**  

If you want to reset your repository to a specific commit, use the commit hash:  

```sh
git reset f96a0c38203e0987b24dcdc6b7b659b2919b7095
```  

This command will reset all changes after the provided commit hash.  

---

## **5. Stashing Changes**  

If you want to temporarily save your changes without committing them:  

```sh
git stash
```  

To retrieve the stashed changes:  

```sh
git stash pop
```  

To delete all stashed changes:  

```sh
git stash clear
```  

---

## **6. Pushing to a Remote Repository**  

### **Add a Remote Repository**  
First, create a repository on GitHub, then copy its URL and run:  

```sh
git remote add origin git_repository_url
```  

### **Verify Remote Repository URLs**  
```sh
git remote -v
```  

### **Push Changes to Remote Repository**  
```sh
git push origin main
```  

---

## **7. Working with Branches**  

### **Create a New Branch**  
```sh
git branch branch_name
```  

### **Check Available Branches**  
```sh
git branch
```  

### **Switch to a Branch**  
```sh
git checkout branch_name
```  

---

## **8. Contributing to a Repository (Forking & Upstream)**  

If you want to contribute to a project but don't have permission to push changes, follow these steps:  

1. **Fork the repository on GitHub.**  
2. **Add the original project as an upstream repository:**  

   ```sh
   git remote add upstream repository_url_of_the_project
   ```  

3. **Verify the remote repositories:**  

   ```sh
   git remote -v
   ```  

4. **Make changes, commit them, and push to your branch.**  
5. **Go to GitHub and open a Pull Request.**  

---

This README provides a structured and easy-to-follow Git workflow. Let me know if you need further refinements! 🚀


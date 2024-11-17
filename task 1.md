# Part 1: Introduction to Version Control and Git #
## Task 1: Install and Configure Git ##
### **1.Configure Git with your username and email:** ###
```bash
git config --global user.name "Your Name" 
git config --global user.email "your-email@example.com" 
```
➤ this cmds are only used first time to setup connection between local and github.

### **2. View your Git configuration:** ###
```bash
git config --list
```
➤ this will give configuartion of our git.

## Task 2: Initialize a Repository ##
### **1. Create a new project folder and navigate to it:** ###
```bash
mkdir MyProject
cd MyProject
```
➤ mkdir will make directory(folder) and cd will change directory to myproject.

### **2. Initialize it as a Git repository:** ###
```bash
git init
```
➤ this cmd will initialize git in that directory then you can use git cmds.

## Task 3: Create a File and Make Multiple Commits ##

### **1. Create a new file and add content:** ###
```bash
echo "My First Project" > README.md
```
➤ this cmd will create new file README.md with text written in " ".

### **2. Stage the file:** ###
```bash
git add README.md
```
➤ this cmd will add README to stagging part.

### **3. Commit the file:** ###
```bash
git commit -m "Initial commit: Added README.md"
```
➤ this cmd will commit added file with message in " ".

### **4. Make changes to the file:** ###
```bash
echo "Added a description" >> README.md
```
➤ this cmd will append text of " " in README.md.

### **5. Stage and commit the changes:** ###
```bash
git add README.md
git commit -m "Updated README with a description"
```
➤ this cmd will add modified file to stagging area and commit with message in " ".

## Task 4: Check Status and Log ##
### **1. Check the repository’s current status:** ###
```bash
git status
```
➤ this cmd will give status of git which files are modified and which file are in stagging area.

### **2. View commit history in detail:** ###
```bash
git log --oneline --graph --decorate
```
➤ --oneline will show commit history in one line, --graph will show graphical branch & merge history, --decorate do decoration to branch names and tags.<br>
<br>
**Example Output:**
```bash
* 2f8d6a2 (HEAD -> main) Updated README with a description
* d3c4b21 Initial commit: Added README.md
```

## Task 5: Create and Clone a Repository ##
### **1. Create a repository on GitHub named example-repo.** ###
### **2. Clone it locally:** ###
```bash
git clone http://codinggita.com/example-repo
```
➤ this will clone any repo in your local.

## Task 6: Understanding the Git Workflow ##
### **Example Workflow:** ###
### **i. Make changes to a file in the working directory:** ###
```bash
echo "Workflow example" > workflow.md
```
➤ this cmd will create new workflow.md file with text written in " ".

### **ii. Stage the file:** ###
```bash
git add workflow.md
```
➤ This cmd will add workflow.md to stagging area.

### **iii. Commit the file to the repository:** ###
```bash
git commit -m "Added workflow example"
```
➤ This will commit added file with message in " ".

---
<br>

# Part 2: Working with Repositories #

## Task 7: Branching and Merging ##
### **1. Create a new branch for a feature:** ###
```bash
git branch feature-login
git checkout feature-login
```
### **Our use:** ###
```bash
git checkout -b feature-login
```
➤ This cmd will create new branch feature-login and checkout will switch to that branch.

### **2. Add a new file and commit changes:** ###
```bash
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```
➤ This cmd will create , add and commit login.html .

### **3. Merge the feature branch into `main`:** ###
```bash
git checkout main
git merge feature-login
```
➤ This cmd will switch to main branch and merge it with feature-login.

## Task 8: Handling Merge Conflicts ##
### **1. Create two branches:** ###
```bash
git branch branch-A
git branch branch-B
```
➤ This cmd will create two branch branch-A and branch-B .

### **2. Modify the same line in `README.md` in both branches.** ###

### **3. Merge `branch-A`into `main`:** ###
```bash
git checkout main
git merge branch-A
```
➤ This cmd will switch to main branch and merge it with branch-A.

### **4. Attempt to merge `branch-B` into `main` (this will cause a conflict):** ###
```bash
git merge branch-B
```
➤ This cmd will give conflict.

### **5. Resolve the conflict manually in `README.md`, then:** ###
```bash
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```
➤ Solve conflict manually and file will be merged .

## Task 9: Renaming and Deleting Branches ##

### **1. Rename a branch:** ###
```bash
git branch -m old-branch-name new-branch-name
```
➤ This cmd will rename branch.

### **2. Delete a branch:** ###
```bash
git branch -d feature-login
```
➤ This cmd will delete branch.

---
<br>

# Part 3: Advanced Git Operations #

## Task 10: Using Git Stash ##
### **1. Make changes to a file but don`t commit:** ###
```bash
echo "Temporary work" >> temp.md
```
➤ This cmd will append content of " " in temp.md .

### **2. Stash the changes:** ###
```bash
git stash
```
➤ This cmd will create stash of all commits.

### **3. View stashed changes:** ###
```bash
git stash list
```
➤ This cmd will list of commits in stash.

### **4. Apply the stashed changes:** ###
```bash
git stash apply
```
➤ this cmd apply stash changes.

### **5. Drop the stash after applying** ###
```bash
git stash drop
```
➤ This cmd remove stash.

## Task 11: Rewriting History with Interactive Rebase ##
### **1. Create multiple commits:** ###
```bash
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
➤ .

### **2. Squash commits into one:** ###
```bash
git rebase -i HEAD~3
```
➤ .
Example: Replace `pick` with `squash` for the second and third commits.

## Task 12: Cherry-Picking Commits ##
### **1. Create a new branch:** ###
```bash
git checkout -b cherry-pick-example
```
➤ .

### **2. Cherry-pick a specific commit from another branch:** ###
```bash
git cherry-pick <commit-hash>
```
➤ .

## Task 13: Tagging Commits ##
### **1. Tag the current commit:** ###
```bash
git tag -a v1.0 -m "Version 1.0 release"
```
➤ .

### **2. Push the tag to the remote repository:** ###
```bash
git push origin v1.0
```
➤ .
Example: Replace `pick` with `squash` for the second and third commits.

## Task 14: Cherry-Picking Commits ##
### **1. Add a remote repository:** ###
```bash
git remote add origin <repository-url>
```
➤ .

### **2. Push your changes to the remote repository:** ###
```bash
git push origin main
```
➤ .

## Task 15: Forking and Contributing ##
### **1. Fork a repository on GitHub.** ###
### **2. Clone the fork locally:** ###
```bash
git clone <forked-repo-url>
```
➤ .

### **3. Create a new branch, make changes, and push:** ###
```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
➤ .
### **4. Open a pull request on GitHub.** ###

---
<br>

# Part 4: Additional Practice #
## Task 16: Simulate Team Collaboration ##
### **1. Create a repository and share it with a friend.** ###
### **2. Both make changes to the same file simultaneously.** ###
### **3. Practice resolving merge conflicts and pushing changes.** ###

## Task 17: Git Ignore ##
### **1. Create a `.gitignore` file:** ###
```bash
echo "node_modules/" > .gitignore
```
➤ .

### **2. Add files and ensure ignored files are not staged:** ###
```bash
git add .
```
➤ .
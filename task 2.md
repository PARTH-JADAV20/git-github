### **Part 1: Git Basics**

#### **Task 1: Install and Configure Git**
1. Install Git from [git-scm.com](https://git-scm.com/).  
2. Configure your global Git settings:  
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```
   ➤ This cmds are used to configure to all repository for current user (globally).
3. Verify the configuration:  
   ```bash
   git config --list
   ```
   ➤ This cmd will give list of configuartion of our git.   

#### **Task 2: Initialize a Repository**
1. Create a directory and initialize it as a Git repository:  
   ```bash
   mkdir MyProject
   cd MyProject
   git init
   ```
   ➤ mkdir will make directory(folder) and cd will change working directory to myproject & git init will initialize git in that directory.
---

### **Part 2: Basic Workflow**

#### **Task 3: Creating and Committing Files**
1. Create a file:  
   ```bash
   echo "Hello Git" > file1.txt
   ```
   ➤ This cmd will create new file file1.txt with text written in " ". 
2. Stage and commit the file:  
   ```bash
   git add file1.txt
   git commit -m "Initial commit: Added file1.txt"
   ```
   ➤ This cmd will add file1.txt to stagging area and commit it with message in " ".

#### **Task 4: Viewing Changes**
1. Modify the file:  
   ```bash
   echo "Git is awesome!" >> file1.txt
   ```
   ➤ This cmd will append message of " " in file1.txt.

2. Check file status and differences:  
   ```bash
   git status
   git diff
   ```
   ➤ This cmds will show status of file like added, modified etc. and diff shows line-by-line difference in file.

#### **Task 5: Undoing Changes**
1. Unstage a staged file:  
   ```bash
   git reset file1.txt
   ```
   ➤ This cmd will undo changes of stagging area before commiting it.
2. Discard uncommitted changes:  
   ```bash
   git checkout -- file1.txt
   ```
   ➤ This cmd will undo changes in file till last commit.

---

### **Part 3: Branching and Merging**

#### **Task 6: Branch Management**
1. Create a branch and switch to it:  
   ```bash
   git checkout -b feature-branch
   ```
   ➤ This cmd will create branch new branch and switch to it.
2. List branches:  
   ```bash
   git branch
   ```
   ➤ This cmd will show in which branch you currently are.

3. Rename a branch:  
   ```bash
   git branch -m feature-branch feature-enhanced
   ```
   ➤ This cmd will rename branch.

#### **Task 7: Merging Branches**
1. Merge `feature-enhanced` into `main`:  
   ```bash
   git checkout main
   git merge feature-enhanced
   ```
   ➤ This cmd will merge feature-enchanced to main branch. 

#### **Task 8: Handling Merge Conflicts**
1. Create two conflicting branches and resolve a conflict manually:  
   ```bash
   git merge <branch-name>
   ```
   ➤ This cmd will merge branch to main branch but it will get conflict.
2. Use:  
   ```bash
   git add <resolved-file>
   git commit
   ```
   ➤ After solving conflict add and commit resolved merged file.

---

### **Part 4: Remote Repositories**

#### **Task 9: Remote Setup**
1. Add a remote repository:  
   ```bash
   git remote add origin https://github.com/your-username/repo.git
   ```
   ➤ This cmd will link local git to specific repository.
2. Verify the remote:  
   ```bash
   git remote -v
   ```
   ➤ This cmd give link of repo its connected.

#### **Task 10: Push and Pull**
1. Push changes to the remote repository:  
   ```bash
   git push -u origin main
   ```
   ➤ This cmd will push the local files to main branch in linked repo.
2. Pull changes from the remote:  
   ```bash
   git pull origin main
   ```
   ➤ This cmd will pull changes made in main branch to your local.

#### **Task 11: Cloning a Repository**
1. Clone a remote repository:  
   ```bash
   git clone https://github.com/your-username/repo.git
   ```
   ➤ This cmd will clone repo to local.

---

### **Part 5: Advanced Git**

#### **Task 12: Stashing Changes**
1. Save uncommitted changes:  
   ```bash
   git stash
   ```
   ➤ This cmd will create stash of all commits.
2. Apply stashed changes:  
   ```bash
   git stash apply
   ```
   ➤ This cmd apply stash.
3. Drop the stash:  
   ```bash
   git stash drop
   ```
   ➤ This cmd remove stash.

#### **Task 13: Tagging Commits**
1. Create and annotate a tag:  
   ```bash
   git tag -a v1.0 -m "Version 1.0 release"
   ```
   ➤ This cmd will tag commit with name as v1.0 and with message in " ".
2. Push the tag to the remote:  
   ```bash
   git push origin v1.0
   ```
   ➤ This will push tagged commit to remote repository.

#### **Task 14: Rewriting Commit History**
1. Use interactive rebase to modify commit messages:  
   ```bash
   git rebase -i HEAD~3
   ```
   ➤ with rebase we can rewrite Git history -i is for interactive and Head~3 is last three commits.
   - Replace `pick` with `edit` or `squash` as needed.

#### **Task 15: Cherry-Picking Commits**
1. Apply a specific commit to another branch:  
   ```bash
   git cherry-pick <commit-hash>
   ```
   This cmd help to pick a commit and apply on current branch.

---

### **Part 6: Collaboration**

#### **Task 16: Forking and Pull Requests**
1. Fork a repository and clone it locally:  
   ```bash
   git clone https://github.com/your-username/forked-repo.git
   ```
   ➤ This cmd will clone forked repo to local.
2. Make changes and push them:  
   ```bash
   git checkout -b fix-typo
   echo "Typo fixed" >> README.md
   git add README.md
   git commit -m "Fixed a typo"
   git push origin fix-typo
   ```
   ➤ This cmd will create new branch, make changes to README file, add and commit the changes and then push to created branch.
3. Open a pull request on GitHub.

#### **Task 17: Simulating Team Collaboration**
1. Simulate a conflict by having two users modify the same file.  
2. Practice resolving the conflict as a team.

---

### **Part 7: Ignoring Files**

#### **Task 18: Using .gitignore**
1. Create a `.gitignore` file:  
   ```bash
   echo "node_modules/" > .gitignore
   git add .gitignore
   git commit -m "Added .gitignore"
   ```
   ➤ Its define rules for directory that should not be tracked, commited, or pushed, git add will add .gitignore to stagging area & then commit for added file.
2. Verify that ignored files are not staged:  
   ```bash
   git status
   ```
   ➤ This cmd show if .gitignore is added or not.

---

### **Part 8: Automation and Cleanup**

#### **Task 19: Cleaning the Repository**
1. Remove untracked files:  
   ```bash
   git clean -f
   ```
   ➤ This cmd will remove untracked file.

#### **Task 20: Aliases and Shortcuts**
1. Create an alias for frequently used commands:  
   ```bash
   git config --global alias.st status
   git config --global alias.cm commit
   ```
   ➤ This cmd will set up aliases for status and commit so they are quicker to type.
2. Use the alias:  
   ```bash
   git st
   git cm -m "Message"
   ```
   ➤ now st for status and cm for commit can used because of created alias.

---
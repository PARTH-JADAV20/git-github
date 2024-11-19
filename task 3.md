### **Task List: Focused on Repository Management, Commits, Branching, and Merging**

### **Part 1: Creating and Cloning Repositories**

#### **Task 1: Create a Local Git Repository**
1. Create a new project folder:  
   ```bash
   mkdir MyProject
   cd MyProject
   ```
   ➤ mkdir will make directory(folder) and cd will change working directory to myproject.
2. Initialize it as a Git repository:  
   ```bash
   git init
   ```
   ➤ git init will initialize git in that directory.
   - **Explanation**: This creates a `.git` folder that stores the repository's metadata and history.

3. Verify the repository status:  
   ```bash
   git status
   ```
   ➤ Shows status of files Untracked, Modified, Staged & Deleted.
   - **Example Output**:  
     ```
     On branch main
     No commits yet
     nothing to commit (create/copy files and use "git add" to track)
     ```

#### **Task 2: Clone a Remote Repository**
1. Clone a GitHub repository:  
   ```bash
   git clone https://github.com/username/repo.git
   ```
   ➤ This cmd clone repo in your local.
   - **Explanation**: This command downloads the repository to your local system.  

2. Verify the cloned repository structure:  
   ```bash
   cd repo
   ls -a
   ```
   ➤ cd is used to go to cloned folder and ls -a to see all files in folder including hidden file like .git .
   - **Output**: The `.git` folder should be present.

---

### **Part 2: Understanding Commits and Commit Messages**

#### **Task 3: Commit Changes Locally**
1. Create a new file and add content:  
   ```bash
   echo "Welcome to Git" > README.md
   ```
   ➤ This cmd will create new README.md file with content that in " ".
2. Stage the file:  
   ```bash
   git add README.md
   ```
   ➤ This cmd moves file to staging area.
   - **Explanation**: `git add` moves changes to the staging area.

3. Commit the staged file:  
   ```bash
   git commit -m "Initial commit: Added README.md"
   ```
   ➤ This cmd will commit added file with message in " ".
   - **Explanation**: Commits save the current state of the repository with a message describing the change.

#### **Task 4: Write Effective Commit Messages**
1. Create a detailed commit message:  
   ```bash
   git commit -m "Added initial version of README.md with project overview"
   ```
   ➤ This cmd will commit added file with effective commit message in " ".
   - **Explanation**: Commit messages should follow conventions such as starting with a capital letter, being concise, and using the imperative mood.

2. Commit multiple files with one message:  
   ```bash
   touch file1.txt file2.txt
   git add .
   git commit -m "Added two new files for feature setup"
   ```
   ➤ This cmds will will creates 2 files and add to staging area and than commit it with effective message in " ".

---

### **Part 3: Viewing Commit History with `git log`**

#### **Task 5: View Detailed Commit History**
1. View full commit logs:  
   ```bash
   git log
   ```
   ➤ This cmd shows commit history.
   - **Explanation**: Shows a detailed list of commits with hash, author, date, and message.

2. View commit history in a compact format:  
   ```bash
   git log --oneline
   ```
   ➤ this cmd shows commit history in onleine.
   - **Example Output**:  
     ```
     e23d8a7 Added initial version of README.md
     f7b3c62 Initial commit: Added README.md
     ```

#### **Task 6: Customize Log Outputs**
1. View logs with a graphical representation:  
   ```bash
   git log --oneline --graph --decorate
   ```
   ➤ This cmd will show commit history in one line with graphical branch & merge history and decorates tags and branch name.
2. Filter logs for a specific file:  
   ```bash
   git log README.md
   ```
   ➤ This cmd will show commit history of particular file.

---

### **Part 4: Understanding Branching and Merging**

#### **Task 7: Understanding Branching**
1. List all branches:  
   ```bash
   git branch
   ```
   ➤ shows the branch your are currently in.
   - **Explanation**: Displays the current branch and all other branches.

2. Create a new branch:  
   ```bash
   git branch feature-branch
   ```
   ➤ This cmd create new branch feature-branch.
   - **Explanation**: Creates a new branch without switching to it.

3. Switch to the new branch:  
   ```bash
   git checkout feature-branch
   ```
   ➤ This cmd is used to switch to diff branch.
   - **Alternative Command**:  
     ```bash
     git checkout -b feature-branch
     ```
     - **Explanation**: Creates and switches to the branch in one command.

---

### **Part 5: Creating and Working with Branches**

#### **Task 8: Make Changes in a Branch**
1. Add content to a file in the new branch:  
   ```bash
   echo "Feature in progress" > feature.txt
   git add feature.txt
   git commit -m "Added feature.txt in feature-branch"
   ```
   ➤ Create new feature.txt file, add to staging area & commit it with some message in " ".


#### **Task 9: Merging Branches**
1. Switch back to the `main` branch:  
   ```bash
   git checkout main
   ```
   ➤ This cmd will switch current branch to main.
2. Merge the `feature-branch` into `main`:  
   ```bash
   git merge feature-branch
   ```
   ➤ This cmd will merge feature-branch to main.
   - **Explanation**: Combines the changes from `feature-branch` into `main`.

---

### **Part 6: Resolving Merge Conflicts**

#### **Task 10: Simulate a Merge Conflict**
1. Modify the same line in a file on two branches:  
   ```bash
   echo "Main branch content" > conflict.txt
   git add conflict.txt
   git commit -m "Added conflict.txt in main branch"
   ```
   ➤ Create new conflict.txt file, add to staging area & commit it with some message in " ".

2. Switch to the other branch and make conflicting changes:  
   ```bash
   git checkout feature-branch
   echo "Feature branch content" > conflict.txt
   git add conflict.txt
   git commit -m "Modified conflict.txt in feature-branch"
   ```
   ➤ Switch to feature-branch Create new conflict.txt file, add to staging area & commit it with some message in " ".

3. Merge `feature-branch` into `main`:  
   ```bash
   git checkout main
   git merge feature-branch
   ```
   ➤ Switch to main branch and merge feature-branch

4. Resolve the conflict by editing the file and choosing the correct version:  
   1.Open `conflict.txt` and decide which changes to keep. <br>
   ➤ Resolve conflict manually.
   2.Stage the resolved file:  
     ```bash
     git add conflict.txt
     ```
   ➤ Add resolved file to staging area.
   3.Commit the merge:  
     ```bash
     git commit -m "Resolved conflict in conflict.txt"
     ```
   ➤ Commit the Resolved/merged file with some message in " ".
---

### **Part 7: Deleting and Renaming Branches**

#### **Task 11: Delete a Branch**
1. Delete a local branch:  
   ```bash
   git branch -d feature-branch
   ```
   ➤ This cmd is used to delete any branch.
   - **Explanation**: This deletes the branch only if it has been fully merged.  

2. Force-delete a branch:  
   ```bash
   git branch -D feature-branch
   ```
   ➤ This cmd is used to delete any branch without merging.
   - **Explanation**: Deletes the branch even if it hasn’t been merged.

#### **Task 12: Rename a Branch**
1. Rename the current branch:  
   ```bash
   git branch -m new-branch-name
   ```
   ➤ This command is used to rename current branch.
2. Rename another branch (not checked out):  
   ```bash
   git branch -m old-branch-name new-branch-name
   ```
   ➤ This cmd is used to rename branch.

---

### **Consolidated Flow Summary**

1. Start by creating and cloning repositories.
2. Learn to commit changes effectively with clear messages.
3. Explore commit history using various `git log` commands.
4. Understand branching and practice creating, switching, and merging branches.
5. Dive into resolving merge conflicts.
6. End by managing branches through deletion and renaming.
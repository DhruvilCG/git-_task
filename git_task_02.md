## **Part 1: Git Basics**

### **Task 1: Install and Configure Git**
1. Install Git from [git-scm.com](https://git-scm.com/).  
2. Configure your global Git settings:  
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```
* set your name and email globally

3. Verify the configuration:

```
git config --list
```
* list all configuration:

## **Task 2: Initialize a Repository**

1. Create a directory and initialize it as a Git repository:

```
mkdir MyProject
cd MyProject
git init
```
* mkdir use for create new folder
* cd use for specify file/folder
* init for initialize repo

* Purpose: Initializes a ```.git``` folder to track changes.

## **Part 2: Basic Workflow**

### **Task 3: Creating and Committing Files**

1. Create a file:

```
echo "Hello Git" > file1.txt
```
* create new file

2. Stage and commit the file:
```
git add file1.txt
git commit -m "Initial commit: Added file1.txt"
```

* add file in satge area
* commit messeage

### **Task 4: Viewing Changes**

1. Modify the file:
```
echo "Git is awesome!" >> file1.txt
```

* modify the file1.txt

2. Check file status and differences:
```
git status
git diff
```
* git status check the cutent state of your repository
* inspect the difference before commiting


### **Task 5: Undoing Changes**
1. Unstage a staged file:
```
git reset file1.txt
```
* only affects the staging area

2. Discard uncommitted changes:
```
git checkout -- file1.txt
```
* Restores the file to its last committed state.


### **Part 3: Branching and Merging**

### **Task 6: Branch Management**

1. Create a branch and switch to it:
```
git checkout -b feature-branch
```

* create new branch

2. List branches:
```
git branch
```

* give list of branch

3. Rename a branch:
```
git branch -m feature-branch feature-enhanced
```
* chages branch name

### **Task 7: Merging Branches**

1. Merge ```feature-enhanced``` into ```main```:

    ```
    git checkout main
    git merge feature-enhanced
    ```

 * merge feature-enhamced to main

 ### **Task 8: Handling Merge Conflicts**

 1. Create two conflicting branches and resolve a conflict manually:

```
git merge <branch-name>
```

2. Create two conflicting branches and resolve a conflict manually:

```
git add <resolved-file>
git commit
```


## **Part 4: Remote Repositories**

### **Task 9: Remote Setup**

1. Add a remote repository:

```
git remote add origin https://github.com/your-username/repo.git
```
* add remote of repositpry

2.
Verify the remote:

```
git remote -v
```

* verify the url og repo.

### **Task 10: Push and Pull**

1. Push changes to the remote repository:

```
git push -u origin main
```

* push file to your local to globle

2. Pull changes from the remote:
```
git pull origin main
```


#### **Task 11: Cloning a Repository**
1. Clone a remote repository:  
   ```bash
   git clone https://github.com/your-username/repo.git
   ```
 * This command copies the repository from the Remote server to Local Machine.

---

### **Part 5: Advanced Git**

#### **Task 12: Stashing Changes**
1. Save uncommitted changes:  
   ```bash
   git stash
   ```
2. Apply stashed changes:  
   ```bash
   git stash apply
   ```
3. Drop the stash:  
   ```bash
   git stash drop
   ```
 *  git stash: Temporarily saves (or stashes) the changes made in the working directory and staging area, then reverts the files to the last committed state.
   
  * git stash apply: Applies the most recent stash (stash@{0}) back to the working directory without removing it from the stash list.

* git stash drop: Removes the most recent stash (stash@{0}) from the stash list.
   ```

#### **Task 13: Tagging Commits**
1. Create and annotate a tag:  
   ```bash
   git tag -a v1.0 -m "Version 1.0 release"
   ```
2. Push the tag to the remote:  
   ```bash
   git push origin v1.0
   ```
 
 * git tag: This command creates a tag on the current commit.
   -a v1.0: The -a flag specifies that you`re creatinf an annotated tag .The v1.0 is the name of the tag.

 *  -m "Version 1.0 release": This provides a message for the tag.

 *  git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.

#### **Task 14: Rewriting Commit History**
1. Use interactive rebase to modify commit messages:  
   ```bash
   git rebase -i HEAD~3
   ```
   - Replace `pick` with `edit` or `squash` as needed.
   
  *  git rebase -i: The -i flag stand for Interactive rebaseb,which allows you to manipulate commits.
   HEAD~3: HEAD~3 means 3 commits before the current commit.


#### **Task 15: Cherry-Picking Commits**
1. Apply a specific commit to another branch:  
   ```bash
   git cherry-pick <commit-hash>
   ```
 * git cherry-pick <commit-hash>: This command takes the changes introduced by the commit with the specified <commit-hash> and applies those changes to your current working branch as a new commit. 
   


### **Part 6: Collaboration**

#### **Task 16: Forking and Pull Requests**
1. Fork a repository and clone it locally:  
   ```bash
   git clone https://github.com/your-username/forked-repo.git
   ```
2. Make changes and push them:  
   ```bash
   git checkout -b fix-typo
   echo "Typo fixed" >> README.md
   git commit -m "Fixed a typo"
   git push origin fix-typo
   ```
3. Open a pull request on GitHub.
   *  Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.

*   git clone <forked-repo-url>: This command clones your forked repository from GitHub to your local machine. 

 *  git checkout -b <branch-name> : This command creates a new branch and switches to it.

  * echo "Typo Fixed" >> README.md: This command adds the text "Typo fixed" to the end of the README.md file.

  * git add README.md: Stages the README.md file for committ.

  * git commit -m "Fixed a typo": Commits the staged changes, with a message.

 *  git push origin fix-typo: This command pushes fix-typo branch and its changes the fork on GitHub.
   

   #### **Task 17: Simulating Team Collaboration**

   1. Simulate a conflict by having two users modify the same file.

   2. Practice resolving the conflict as a team.
   
   Explaination :- 1. Create two branches:
   ```
   git branch branch-A
   git branch branch-B
   ```
   2. Modify the same line in README.md in both branches.

   3. Merge branch-A into main:
   ```
   git checkout main
   git merge branch-A
   ```
   4. Attempt to merge branch-B into main (this will cause a conflict):
   ```
   git merge branch-B 
   ```
   5. Resolve the conflict manually in README.md, then:
   ```
   git add README.md
   git commit -m "Resolved merge conflict between branch-A and branch-B"
   ```
   
---

### **Part 7: Ignoring Files**

#### **Task 18: Using .gitignore**
1. Create a `.gitignore` file:  
   ```bash
   echo "node_modules/" > .gitignore
   git add .gitignore
   git commit -m "Added .gitignore"
   ```
2. Verify that ignored files are not staged:  
   ```bash
   git status
   ```
  * echo "node_modules/" > .gitignore: This command creates a .gitignore file and adds the line node_modules/ to it.

  * git add .: The command stages all changes in the current directory for commit.

 *  git commit -m "":

 *  git status: This command shows the current state of your working directory and staging area.
   


### **Part 8: Automation and Cleanup**

#### **Task 19: Cleaning the Repository**
1. Remove untracked files:  
   ```bash
   git clean -f
   ```
  * This command is used to remove untracked files from your working directory.
   

#### **Task 20: Aliases and Shortcuts**
1. Create an alias for frequently used commands:  
   ```bash
   git config --global alias.st status
   git config --global alias.cm commit
   ```
2. Use the alias:  
   ```bash
   git st
   git cm -m "Message"
   ```
* git config: Modifies Git's configuration files.
  * --global: Applies the configuration globally for all repositories on your system.

 *  alias.st: Creates a shortcut for the git status command. After this, you can type git st instead of git status.

 *  alias.cm: Creates a shortcut for the git commit command. After this, you can type git cm instead of git commit.
   
 *  git st: Execute the git status.

 *  git cm -m "M": Execute the git commit im "message".

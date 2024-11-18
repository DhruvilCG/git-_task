
# **Part 1: Introduction to Version Control and Git**

## **Task 1: Install and Configure Git**

1. Configure Git with your username and email:
```
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
* set your name and email globally

2. View your Git configuration:
```
git config --list
```
* list all confrigration

## Task 2: Initialize a Repository

1. Create a new project folder and navigate to it:

```
mkdir MyProject
cd MyProject
```
* mkdir used for create new folder
* cd use for go to a specific folder/file

2. Initialize it as a Git repository:
```
git init
```
* initialize git repository
* create .git hidden folder

## Task 3: Create a File and Make Multiple Commits

1. Create a new file and add content:

```
echo "My First Project" > README.md
```
* create a readme.md file

2. Stage the file:

```
git add README.md
```
* add file in staging area

3. Commit the file:
 * commit the messege

4. Make changes to the file:
```
echo "Added a description" >> README.md
```
* changes in file

5. Stage and commit the changes:

```
git add README.md
git commit -m "Updated README with a description"
```
* git add use for add file in stagging area
* git commit use for commit messeage

## Task 4: Check Status and Log

1. Check the repository’s current status:

```
git status
```
* check repository status

2. View commit history in detail:
```
git log --oneline --graph --decorate
```
* view commit messeage history

Example Output:
```
* 2f8d6a2 (HEAD -> main) Updated README with a description
* d3c4b21 Initial commit: Added README.md
```

## Task 5: Create and Clone a Repository

1. Task 5: Create and Clone a Repository
2. Clone it locally:
```
git clone http://codinggita.com/example-repo
```
* clone the repository global to local

## Task 6: Understanding the Git Workflow
* Example Workflow:

i. Make changes to a file in the working directory:
```
echo "Workflow example" > workflow.md
```
* changes in workflow example

ii. Stage the file:
```
git add workflow.md
```
* add file in stage area

iii. Commit the file to the repository:

```
git commit -m "Added workflow example"
```
* commit the messeage

# **Part 2: Working with Repositories**

## Task 7: Branching and Merging

1. Create a new branch for a feature:
```
git branch feature-login
git checkout feature-login
```
* git branch use create new branch
* git checkout switching branches

Or use:
```
git checkout -b feature-login
```
* checkout -b for create new branch

2. Add a new file and commit changes:
```
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```
* echo for create file
* add for add file stag area
* commit for messeage

3. Merge the feature branch into ```main```:
```
git checkout main
git merge feature-login
```
* checkout for switching branch to main
* merge for  merge two branches

## Task 8: Handling Merge Conflicts

1. Create two branches:

```
git branch branch-A
git branch branch-B
```
*  git branch use for create branch

2. Modify the same line in README.md in both branches.

3. Merge branch-A into main:
 ```
 git checkout main
 git merge branch-A
 ```

* switching branch into main and merge main into branc-A  branches

4. Attempt to merge branch-B into main (this will cause a conflict):

```
git merge branch-B
```
* merge branch main into branch-B

5. Resolve the conflict manually in ```README.md```, then:

```
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```
* add readme file in stagging area and commit messeage

## Task 9: Renaming and Deleting Branches

1. Rename a branch:
```
git branch -m old-branch-name new-branch-name
``` 
* rename branch name

2.Delete a branch:

```
git branch -d feature-login
```

*  branch -d for delete branch


# Part 3: Advanced Git Operations

## Task 10: Using Git Stash

1. Make changes to a file but don’t commit:  
   ```bash
   echo "Temporary work" >> temp.md
   ```
2. Stash the changes:  
   ```bash
   git stash
   ```
3. View stashed changes:  
   ```bash
   git stash list
   ```
4. Apply the stashed changes:  
   ```bash
   git stash apply
   ```
5. Drop the stash after applying:  
   ```bash
   git stash drop
   ```
* echo:  Output the text "Workflow Example" to the file.
   >>: Unlike >, this appends the text to the file without overwriting its existing content.

 *  git stash: Temporarily saves (or stashes) the changes made in the working directory and staging area, then reverts the files to the last committed state.

 *  git stash list: Displays a list of all stashes in your repository. Each stash is identified by an index 

*   git stash apply: Applies the most recent stash (stash@{0}) back to the working directory without removing it from the stash list.

*   git stash drop: Removes the most recent stash (stash@{0}) from the stash list.
   

## Task 11: Rewriting History with Interactive Rebase

1. Create multiple commits:
```
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
2. Squash commits into one:
```
git rebase -i HEAD~3
```

* echo "Text" > <file-name>: echo create a file and write Text into it.
* git add <file-name>: Stage the file to be commited. 
* git commit -m "message": Create the first commit with message.

* git rebase -i: The -i flag stand for Interactive rebaseb,which allows you to manipulate commits.
HEAD~3: HEAD~3 means 3 commits before the current commit.

## Task 12: Cherry-Picking Commits

1. Create a new branch:
```
git checkout -b cherry-pick-example
```
2. Cherry-pick a specific commit from another branch:
```
git cherry-pick <commit-hash>
```
* This Command Create a new branch and switch into it (IN one Step).

* git cherry-pick <commit-hash>: This command takes the changes introduced by the commit with the specified <commit-hash> and applies those changes to your current working branch as a new commit. 

## Task 13: Tagging Commits

1. Tag the current commit:
```
git tag -a v1.0 -m "Version 1.0 release"
```
2. Push the tag to the remote repository:
```
git push origin v1.0
```
* git tag: This command creates a tag on the current commit.
-a v1.0: The -a flag specifies that you`re creatinf an annotated tag .The v1.0 is the name of the tag.

* -m "Version 1.0 release": This provides a message for the tag.

* git push origin v1.0: This command pushes the tag (v1.0) to the remote repository.

## Task 14: Working with Remote Repositories

1. Add a remote repository:
```
git remote add origin <repository-url>
```
2. Push your changes to the remote repository:
```
git push origin main
```
* git remote add origin: This command adds a remote repository to your local Git repository. The remote repository is where your code can be pushed or pulled from.

* git push origin main: This command pushes your local changes to the remote repository.


## Task 15: Forking and Contributing

1. Fork a repository on GitHub.

2. Clone the fork locally:
```
git clone <forked-repo-url>
```
3. Create a new branch, make changes, and push:
```
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
4. Open a pull request on GitHub.
* Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.

* git clone <forked-repo-url>: This command clones your forked repository from GitHub to your local machine. 

* git checkout -b <branch-name> : This command creates a new branch and switches to it.

* echo "Typo Fixed" >> README.md: This command adds the text "Typo fixed" to the end of the README.md file.

* git add README.md: Stages the README.md file for committ.

* git commit -m "Fixed a typo": Commits the staged changes, with a message.

* git push origin fix-typo: This command pushes fix-typo branch and its changes the fork on GitHub.




# Part 4: Additional Practice

## Task 16: Simulate Team Collaboration

1. Create a repository and share it with a friend.
2. Both make changes to the same file simultaneously.
3. Practice resolving merge conflicts and pushing changes.


## Task 17: Git Ignore

1. Create a .gitignore file:
```
echo "node_modules/" > .gitignore
```
2. Add files and ensure ignored files are not staged:
```
git add .
```
* echo "node_modules/" > .gitignore: This command creates a gitignore file and adds the line node_modules/ to it.

* git add .: The command stages all changes in the current directory for commit.





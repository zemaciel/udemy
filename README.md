# README

# Practical Guide for Git

## Installing Git

<aside>
▶️ The Git & Github Bootcamp - Sections 3 and 4

</aside>

### Check the version of your git

```python
git --version
```

Use version above 2.24.3

### Configuring git name and email

Check for your username:

```bash
git config user.name
```

To change the user name for a specific repository:

Navigate to the directory of the repository in your terminal and use:

```bash
git config user.name "Your New Name"
```

Set username (Change the global user name (it will affect all repositories on your computer)):

```bash
git config --global user.name "Colt Steele"
```

This can be used to change the global user name (it will affect all repositories on your computer.

Check for user email

```bash
git config user.gitemail
```

Set email

```bash
git config --global user.email
```

## Start a new git

```bash
git init
```

- This will create a hidden folder (`.git`) inside of the folder you choose to be the repository
- If that folder is deleted, it will delete the history and the folder won't be a repo anymore
- **DO NOT INIT A REPO INSIDE OF A REPO**
- Before running `git init`, use `git status` to verify you are not currently inside of a repo.

### Changing the name of the master branch to main branch

```bash
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
```

```bash
git config --global init.defaultBranch main
```

### Renaming Master branch on VS Code (ChatGTP)

### **Renaming Locally and Pushing Changes:**

1. **Rename the branch locally:**
    
    Open your terminal or integrated terminal in VSCode and navigate to your local repository. Then, run the following commands:
    
    ```bash
    bashCopy code
    git branch -m master main
    
    ```
    
    This renames the current branch from "master" to "main".
    
2. **Change the default branch:**
    
    Update the default branch on GitHub or any remote repository where your code is hosted. Go to your repository settings, find the option to change the default branch, and set it to "main".
    
3. **Push the changes:**
    
    After renaming the branch locally and updating the default branch on the remote, you need to push your changes:
    
    ```bash
    bashCopy code
    git push -u origin main
    
    ```
    
    This command pushes the changes to the remote repository and sets the "main" branch as the new default.
    

### **Update VSCode:**

While VSCode doesn't have a specific setting to change the branch name, if you've been working with the default branch "master" in your VSCode environment, you might need to update your settings and configurations to reflect the new branch name "main". For instance, you might have tasks or scripts referencing the branch name. Check those configurations to ensure they now reference the "main" branch.

After making these changes, you should see the updated branch name in your VSCode environment.

Remember, before making any changes, especially changing the default branch on remote repositories, ensure you have backups or are confident in your repository state to avoid any accidental data loss.

# Git Hub and Remote Repositories

<aside>
▶️ Web Dev Bootcamp - Section 27 - Lesson 218

</aside>

- Create a new repository in GitHub
- Copy the address of your new git repository
- 

```bash
https://github.com/zemaciel/**udemy.git**
```

In the terminal use these commands to push an existing repository from the command line

```bash
…or 
git remote add origin https://github.com/zemaciel/**udemy.git**
~~git branch -M main~~
git push -u origin main
```
# Connecting VS Code to GitHub Cheat Sheet

This cheat sheet explains how to connect your local machine to GitHub using **VS Code** and push your local changes to GitHub. Follow these steps to seamlessly manage your code between your local machine and GitHub.

## 1. Install Git
Ensure Git is installed on your machine. If it's not installed, follow the instructions here: [Git Downloads](https://git-scm.com/downloads).

Verify the installation:
```bash
git --version
```

## 2. Set Up Git in VS Code
If Git is installed, VS Code will automatically detect it. Open **VS Code**, and you can manage Git commands directly in the built-in terminal.

## 3. Configure Git (First Time Setup)
Before using Git, configure your username and email. This information will be linked to your commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## 4. Create a New Repository on GitHub
1. Log in to [GitHub](https://github.com/).
2. Click on the **New Repository** button.
3. Name your repository and click **Create Repository**. You will get the URL for the repository, which will be used later.

## 5. Initialize Git in Your Project Folder
Open VS Code and navigate to your project directory in the terminal. Initialize Git in the folder:

```bash
git init
```

## 6. Add Your GitHub Repository as a Remote
Link your local repository to your GitHub repository by adding the remote URL from step 4:

```bash
git remote add origin https://github.com/username/repo-name.git
```

## 7. Stage and Commit Your Files
After making changes to your files in VS Code, you need to stage and commit them to the local repository:

### Stage all files:
```bash
git add .
```

### Commit with a message:
```bash
git commit -m "Your commit message"
```

## 8. Push Your Changes to GitHub
Once the files are staged and committed locally, push them to GitHub:

```bash
git push -u origin main
```

## 9. Pull Changes from GitHub
To keep your local repository in sync with the GitHub repository, pull the latest changes before making updates:

```bash
git pull origin main
```

## 10. View Git Changes in VS Code
In VS Code, you can view file changes directly:
1. Open the **Source Control** tab in the left sidebar.
2. You will see modified, staged, and untracked files. You can stage or discard changes here.

## 11. Create and Switch Between Branches
To work on a new feature, create a new branch:
```bash
git checkout -b new-feature
```

To switch between branches:
```bash
git checkout branch-name
```

## 12. Push Branches to GitHub
After committing changes to your new branch, push the branch to GitHub:
```bash
git push origin new-feature
```

## 13. Merge a Branch into Main
When you're done with the feature, merge it into the main branch:

1. Switch to the main branch:
```bash
git checkout main
```

2. Merge the feature branch:
```bash
git merge new-feature
```

## 14. Resolve Merge Conflicts
If you encounter merge conflicts, VS Code will show you the conflicting files. You can choose which changes to keep and then commit the resolved files:
```bash
git add .
git commit -m "Resolved merge conflicts"
```

This cheat sheet helps you connect your local VS Code environment to GitHub, keep your repositories synchronized, and manage your code seamlessly between your laptop and GitHub. Keep this reference handy for your GitHub workflows!

# Removing All Git Commit History

This guide explains how to completely remove all commit history from a Git repository and create a clean repository while keeping the current files intact.

## Steps

### 1. Navigate to Your Repository
```bash
cd AutoGen_agentic_framework_walkthrough
ls
```
Ensure you are in the correct repository directory.

### 2. Create a New Orphan Branch
```bash
git checkout --orphan new_branch
```
This creates a new branch without any commit history.

### 3. Stage and Commit All Files
```bash
git add .
git commit -m "Initial commit"
```
This stages all files and creates a new initial commit on the orphan branch.

### 4. Delete the Old Branch
```bash
git branch -D main
```
This deletes the old branch (`main`) to remove its commit history.

### 5. Rename the New Branch to `main`
```bash
git branch -m main
```
This renames the orphan branch to `main`.

### 6. Force Push to Update Remote Repository
```bash
git push -f origin main
```
This force pushes the new branch to the remote repository, overwriting its history.

### 7. Verify Command History
```bash
history
```
This allows you to review the commands executed.

## Notes
- **Warning**: These steps will **permanently delete all commit history** from the repository.
- Ensure you have a backup if commit history is important for any reason.
- Force pushing (`git push -f`) can overwrite remote history and impact collaborators.

## Why Use These Steps?
- To reset a repository while preserving files.
- To remove sensitive or unwanted history from a Git project.

# Git Merge Conflict Resolution Demo

## Overview
This repository demonstrates Git branch creation, merging, and resolving merge conflicts.

## Repository Structure
- `main` branch: Contains the initial commit and changes.
- `feature-branch`: A branch that introduces changes to `file.txt` that will cause a merge conflict.

## Steps Followed

### 1. Initialize a Git Repository
```bash
git init
echo "Initial content" > file.txt
git add file.txt
git commit -m "Initial commit"
git remote add origin <your-repository-url>
git push origin main
```

### 2. Create a Feature Branch
```bash
git checkout -b feature-branch
echo "Feature branch changes" >> file.txt
git add file.txt
git commit -m "Updated file.txt in feature-branch"
git push origin feature-branch
```

### 3. Modify the File in Main Branch
```bash
git checkout main
echo "Main branch changes" >> file.txt
git add file.txt
git commit -m "Updated file.txt in main branch"
git push origin main
```

### 4. Merge Feature Branch into Main
```bash
git merge feature-branch
```
A merge conflict will occur because both branches modified `file.txt`.

### 5. Resolve the Merge Conflict
Open `file.txt` and manually edit the conflicting section.

#### Before Resolution:
```
<<<<<<< HEAD
Main branch changes
=======
Feature branch changes
>>>>>>> feature-branch
```

#### After Resolution:
```
Main branch changes
Feature branch changes
```

### 6. Complete the Merge
```bash
git add file.txt
git commit -m "Resolved merge conflict in file.txt"
git push origin main
```

## Viewing Commit History
To visualize the commit history:
```bash
git log --oneline --graph --all
```

## Conclusion
This repository serves as a reference for handling merge conflicts in Git. If you have any questions, feel free to raise an issue!

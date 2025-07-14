# 🧠 Git & GitHub Basics

---

## 📌 Why Git?

* ✅ **Version Control** – Keeps track of previous versions without saving multiple copies.
* 🔁 **To Share Code** – Anyone can download it from Git.
* 🤝 **To Collaborate** – Others can make changes to the original code and we can merge those changes.
* 🌍 **Open-source** – Available for everyone and community-driven.
* 🌿 **Has Branches** – Enables parallel development workflows.

---

## 🖥️ Using Git Locally

Git on a local computer has **3 layers**:

1. **Local Folder**
2. **Staging Area**

   * `git add <file>` → Adds a specific file
   * `git add .` → Adds all changes
3. **Local Repository**

   * `git commit` → Moves changes from staging to local repo

---

## ☁️ Using a Git Provider

* `git push` → Pushes committed files to the remote repository
* `git pull` → Pulls files from remote to local

---

## 🔄 Git is a Distributed Version Control (DVC)

### What is Centralized VC?

* Only the **latest version** is fetched.
* **No history** of changes.

### What is Distributed VC?

* Latest file **with history** is fetched.
* **No loss** of old files.

---

## 🔧 Practical Git Commands

```bash
git init                         # Initialize a Git repository
git status                      # Check working directory state
git add "file-name"             # Add specific file to staging
git add .                       # Add all files to staging
git commit -m "message"         # Commit with a message
git push                        # Push to remote
git pull                        # Pull from remote
git diff                        # Show uncommitted changes
git diff --cached              # Show staged changes
git clone <repo-link>           # Clone a repo

# Logs & History
git log                         # View full commit history
git log -p                      # View commit diffs
git log --graph                # Visual representation
git log --grep="term"           # Search in commits
git show <commit-hash>         # Show a specific commit
git log --oneline              # Condensed history

# Restore & Revert
git restore --staged <file>     # Unstage a file
git restore <file>              # Discard local changes
git checkout <commit-hash>      # Checkout a previous commit
git revert <commit-id>          # Create a revert commit

# Remote Repositories
git remote -v                         # Show current remotes
git remote add origin <url>          # Add a new remote repository
git remote remove origin             # Remove a remote
git push -u origin main              # Push local branch to remote and set upstream
git branch -u origin/main            # Track remote branch
git fetch origin                     # Fetch changes from remote
git push origin <branch-name>       # Push specific branch
git pull origin <branch-name>       # Pull from specific branch

# Deleting & Folder Tricks
# - To delete: remove locally and push the change
# - Empty folders aren't tracked; use:
touch .gitkeep                 # Add to empty folder
```

---

## 🔹 Examples

### Initialize a Repo and Push First Commit

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <repo-URL>
git push -u origin main
```

### Reverting a Commit

```bash
git log --oneline     # Copy the commit ID
git revert abc123     # Revert that commit
```

### Cloning and Making Changes

```bash
git clone <repo-url>
cd repo-folder
touch newfile.js
git add newfile.js
git commit -m "Add newfile.js"
git push
```

---

## 🔬 Best Practices

* Always write **meaningful commit messages**.
* Use **branches** for new features or fixes.
* Pull before you push to **avoid merge conflicts**.
* Avoid committing **sensitive data** or `.env` files.
* Use `.gitignore` to exclude unnecessary files.
* Use **`.gitkeep`** to include empty folders.

---

## ❓ FAQs

###  Why isn't my folder showing in the Git repo?

> Git doesn't track empty folders. Add a `.gitkeep` file inside.

###  I made a mistake. How do I undo a commit?

> Use `git revert <commit-id>` or `git checkout <commit-id>` to move to that state.

###  What's the difference between `git reset` and `git revert`?

> `reset` modifies history and should be used carefully. `revert` creates a new commit that undoes changes.

###  How to remove a file from staging?

> Use `git restore --staged <file-name>`

###  How to discard all local changes?

> Use `git restore .`

---

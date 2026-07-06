
# 1. View Remotes

## 🔍 List all remotes

```bash
git remote
```

### Usage:

Shows the names of all configured remotes (e.g., `origin`, `upstream`).

---

## 🔍 Detailed remote URLs

```bash
git remote -v
```

### Usage:

Displays fetch and push URLs for each remote.

---

## 🔍 Show a specific remote

```bash
git remote show origin
```

### Usage:

Displays detailed info about a remote:

- branches tracked
    
- fetch/push URLs
    
- sync status
    

---

# 2. Add Remote

## ➕ Add a new remote

```bash
git remote add origin https://github.com/user/repo.git
```

### Usage:

Adds a new remote repository.

### Example:

```bash
git remote add upstream https://github.com/original/repo.git
```

---

# 3. Change Remote URL

## 🔄 Change existing remote URL

```bash
git remote set-url origin https://github.com/user/new-repo.git
```

### Usage:

Updates the URL of an existing remote without removing it.

---

## 🔄 Set separate fetch/push URLs

```bash
git remote set-url --push origin https://github.com/user/repo.git
git remote set-url --fetch origin https://github.com/user/repo.git
```

### Usage:

Useful if fetch and push use different repositories (rare cases).

---

# 4. Rename Remote

## ✏️ Rename remote

```bash
git remote rename origin upstream
```

### Usage:

Renames a remote (commonly used when setting up forks).

---

# 5. Remove Remote

## ❌ Remove a remote

```bash
git remote remove origin
```

OR

```bash
git remote rm origin
```

### Usage:

Deletes a remote reference from your local repo.

---

# 6. Fetch from Remote

## 📥 Fetch updates

```bash
git fetch origin
```

### Usage:

Downloads commits, branches, and tags from remote (does NOT merge).

---

## 📥 Fetch all remotes

```bash
git fetch --all
```

### Usage:

Fetches updates from all configured remotes.

---

# 7. Pull from Remote

## ⬇️ Fetch + merge

```bash
git pull origin main
```

### Usage:

Fetches and merges remote branch into current branch.

---

## ⬇️ Rebase instead of merge

```bash
git pull --rebase origin main
```

### Usage:

Keeps commit history linear.

---

# 8. Push to Remote

## ⬆️ Push changes

```bash
git push origin main
```

### Usage:

Uploads local commits to remote branch.

---

## ⬆️ Set upstream branch

```bash
git push -u origin main
```

### Usage:

Links local branch to remote branch for future push/pull shortcuts.

---

## ⬆️ Push all branches

```bash
git push --all origin
```

### Usage:

Pushes all local branches to remote.

---

## ⬆️ Push tags

```bash
git push --tags
```

### Usage:

Uploads all tags to remote.

---

# 9. Cleanup Remote References

## 🧹 Remove deleted remote branches locally

```bash
git remote prune origin
```

### Usage:

Cleans up references to branches deleted on remote.

---

## 🧹 Auto prune during fetch

```bash
git fetch --prune
```

### Usage:

Fetches updates and removes stale remote branches.

---

# 10. Advanced Remote Info

## 📊 Get remote URL only

```bash
git config --get remote.origin.url
```

### Usage:

Prints the URL of a remote.

---

## 📊 List all remote config

```bash
git config --get-regexp remote
```

### Usage:

Shows full configuration of all remotes.

---

# 11. Typical Fork Setup (Recommended)

```bash
git remote rename origin upstream
git remote add origin https://github.com/yourname/repo.git
```

### Meaning:

- `origin` → your fork (push here)
    
- `upstream` → original repo (pull updates from here)
    

---

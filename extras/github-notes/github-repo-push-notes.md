# 🚀 Push Local Repository to GitHub from Scratch

This guide helps you push a local project folder to GitHub using Git.

---

## ✅ Prerequisites

* Git installed: `git --version`
* GitHub account
* A new GitHub repo created (without README)

---

## 🛠️ Step-by-Step

```bash
# Step 1: Navigate to your local project
cd /path/to/your/project

# Step 2: Initialize Git
git init

# Step 3: Add files to staging
git add .

# Step 4: Commit the files
:git commit -m "Initial commit"

# Step 5: Add remote GitHub repo (replace <URL> with your repo URL)
git remote add origin https://github.com/your-username/your-repo.git

# Step 6: Push to GitHub main branch
git branch -M main
git push -u origin main
```

---

## 🔍 Notes

* Replace `your-username/your-repo` with your actual GitHub repo path.
* Make sure the GitHub repo is empty (no README/License) to avoid push conflicts.
* Use `git status` to verify what's staged or committed.

---


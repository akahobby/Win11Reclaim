# Push Win11Reclaim to GitHub

## 1. Create the repo on GitHub

1. Go to [github.com/new](https://github.com/new).
2. **Repository name:** `Win11Reclaim`
3. **Owner:** your account (e.g. `akahobby`)
4. **Visibility:** Public (or Private if you prefer)
5. Do **not** add a README, .gitignore, or LICENSE (you already have them locally).
6. Click **Create repository**.

## 2. Point this repo at your new remote

In PowerShell, from the project folder:

```powershell
cd "C:\Users\Administrator\Documents\win11debloat\Win11Debloat"

# Remove the old upstream (Raphire/Win11Debloat)
git remote remove origin

# Add your repo (replace akahobby with your GitHub username if different)
git remote add origin https://github.com/akahobby/Win11Reclaim.git
```

## 3. Stage, commit, and push

```powershell
# Stage everything (new .gitignore will exclude Logs/, etc.)
git add -A
git status

# Commit
git commit -m "Win11Reclaim: rebrand, UI overhaul, Get.ps1 and README for GitHub"

# Push (use main if your default branch is main)
git push -u origin master
```

If GitHub created the repo with a `main` branch and you want to use that:

```powershell
git branch -M main
git push -u origin main
```

## 4. Optional: delete old getter script

You have both `Get.ps1` in the root (new downloader) and `Scripts/Get.ps1` (old). If you only want the root one:

```powershell
git rm Scripts/Get.ps1
git commit -m "Remove duplicate Get.ps1 from Scripts"
git push
```

Done. Your repo will be at **https://github.com/akahobby/Win11Reclaim**.

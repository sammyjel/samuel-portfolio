# Publish this site to your GitHub (one-time)

Your site is already a git repo with everything committed. I couldn't push for you because
GitHub needs an interactive login I can't do in the background. Run these **4 commands**
once in PowerShell — copy-paste the whole block:

```powershell
cd C:\Users\sammy\Downloads\samuel-portfolio

# 1. Log in (opens your browser; choose: GitHub.com -> HTTPS -> Login with a web browser)
gh auth login

# 2. Create the repo under your account and push everything
gh repo create samuel-portfolio --public --source=. --remote=origin --push

# 3. Turn on GitHub Pages (serve the site from the main branch)
gh api -X POST "repos/sammyjel/samuel-portfolio/pages" -f "source[branch]=main" -f "source[path]=/"
```

**Your live GitHub Pages URL will be:**
```
https://sammyjel.github.io/samuel-portfolio/
```
(It can take 1-2 minutes to go live the first time.)

---

## Updating it later
After I make future changes, publish them with:
```powershell
cd C:\Users\sammy\Downloads\samuel-portfolio
git add -A
git commit -m "update"
git push
```
GitHub Pages redeploys automatically on every push.

## Notes
- The repo is **public** (needed for free GitHub Pages). If you want it private, you'd need
  GitHub Pro, or keep using the public repo.
- Your headshot (`assets/samuel.jpg`) is committed, so it ships with the site.
- All asset links are relative, so the site works fine at the `/samuel-portfolio/` sub-path.

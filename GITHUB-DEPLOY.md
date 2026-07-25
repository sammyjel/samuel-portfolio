# Push this site to your GitHub (one-time)

Everything is already done for you:
- the folder is a git repo with all changes committed
- the remote `origin` is already set to `https://github.com/sammyjel/samuel-portfolio.git`
- the branch is `main`

I could not run the final push myself, because GitHub needs an interactive login
(a browser popup) that the background environment blocks. So run this in **your own**
PowerShell window — it will open a browser the first time to log you in:

```powershell
cd C:\Users\sammy\Downloads\samuel-portfolio
git push -u origin main
```

If a login window appears, sign in to GitHub and allow it, then the push completes.

### If `git push` says "Authentication failed" or hangs
Log in with the GitHub CLI first, then push:
```powershell
gh auth login          # choose: GitHub.com -> HTTPS -> Login with a web browser
git push -u origin main
```

## Then turn on GitHub Pages (makes it a live website)
After the push succeeds:
```powershell
gh api -X POST "repos/sammyjel/samuel-portfolio/pages" -f "source[branch]=main" -f "source[path]=/"
```
Or on the website: your repo -> **Settings -> Pages -> Source: Deploy from a branch -> main -> /(root) -> Save**.

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

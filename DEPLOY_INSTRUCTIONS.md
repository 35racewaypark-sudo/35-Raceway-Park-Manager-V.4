# 35 Raceway Park — How to Deploy Updates

Every time you have a new version of the app, follow these steps. Copy/paste each command exactly.

---

## Step 1 — Open your terminal (Git Bash) and go to your project folder

```bash
cd ~/35-Raceway-Park-Manager-V.4
```

---

## Step 2 — Copy the new file into the public folder

Replace the filename if it's different, but always rename it to index.html at the end:

```bash
cp ~/Documents/35-Raceway-Park-Manager-V.4-main/YOURFILENAME.html public/index.html
```

**Example:**
```bash
cp ~/Documents/35-Raceway-Park-Manager-V.4-main/race_manager_v4_1.html public/index.html
```

> If you also have a new logo or any other image, copy that too:
> ```bash
> cp ~/Documents/35-Raceway-Park-Manager-V.4-main/35_Logo2.png public/
> ```

---

## Step 3 — Deploy to Firebase (makes it live)

```bash
firebase deploy --only hosting
```

Wait for it to finish. It will show you your live URL when it's done.

---

## Step 4 — Save to GitHub (backs up your code)

```bash
git add -A
git commit -m "Update race manager - v4.1"
git push origin main
```

> Change the message in quotes to describe what changed. It's just for your own records.

---

## That's it. Done.

| Step | What it does |
|------|-------------|
| Step 1 | Makes sure you're in the right folder |
| Step 2 | Puts your new file in place |
| Step 3 | Pushes it live to the web |
| Step 4 | Saves everything to GitHub as a backup |

---

## Troubleshooting

**"command not found: firebase"**
→ Run this first, then try again:
```bash
npm install -g firebase-tools
firebase login
```

**"fatal: not a git repository"**
→ You're in the wrong folder. Run Step 1 again.

**"rejected - Updates were rejected"**
→ Someone else pushed a change. Run this first:
```bash
git pull origin main
```
Then redo Step 4.

**The site looks the same after deploy**
→ Hard refresh your browser: Ctrl + Shift + R

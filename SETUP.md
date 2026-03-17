# Setup Guide — Between Versions

A plain-English walkthrough. No prior experience needed.

---

## What you need first

- [ ] [VS Code](https://code.visualstudio.com) — free code editor (where you'll write and edit)
- [ ] [Git](https://git-scm.com/downloads) — installs the `git` command on your laptop
- [ ] A free [GitHub](https://github.com) account
- [ ] A free [Netlify](https://netlify.com) account

---

## Step 1 — Open your project in VS Code

1. Open VS Code
2. Go to **File → Open Folder**
3. Select your `between-versions` folder

You'll see all your files in the sidebar on the left.

---

## Step 2 — Test the site locally

Open a terminal in VS Code (**Terminal → New Terminal**) and run:

```bash
python3 -m http.server 8000
```

Then open your browser and go to:

```
http://localhost:8000
```

You should see your site. When you're done, press `Ctrl+C` in the terminal to stop it.

---

## Step 3 — Put it on GitHub (first time only)

### 3a. Create a new repository on GitHub

1. Go to [github.com](https://github.com) and log in
2. Click the **+** icon (top right) → **New repository**
3. Name it: `between-versions`
4. Set it to **Public**
5. Do NOT check "Add README" (you already have one)
6. Click **Create repository**

### 3b. Connect your folder to GitHub

In the VS Code terminal, run these commands one by one:

```bash
git init
git add .
git commit -m "first version — between versions"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/between-versions.git
git push -u origin main
```

> Replace `YOUR-USERNAME` with your actual GitHub username.

Your files are now on GitHub. 🎉

---

## Step 4 — Deploy with Netlify (first time only)

1. Go to [netlify.com](https://netlify.com) and log in
2. Click **Add new site → Import an existing project**
3. Choose **GitHub**
4. Authorize Netlify to access your GitHub
5. Select your `between-versions` repository
6. Leave all settings as they are — click **Deploy site**

Netlify will give you a URL like `random-name-123.netlify.app`.

### Rename your site

1. In Netlify dashboard → **Site configuration → Change site name**
2. Set it to `betweenversions` (or whatever's available)
3. Your site is now live at `betweenversions.netlify.app`

---

## Step 5 — The everyday workflow (after setup)

Every time you write a new essay or make changes:

```bash
git add .
git commit -m "add essay: your essay title here"
git push
```

That's it. Netlify detects the push and redeploys automatically within ~30 seconds.

---

## How to write a new essay

1. Go to the `essays/` folder
2. Copy `essay-template.html`
3. Rename it — e.g. `essay-004.html`
4. Open it in VS Code
5. Find every line marked `<!-- CHANGE: ... -->` and update it
6. Write your essay between the `<p>` tags
7. Add it to `essays.html` (copy an existing `essay-row` block and update the text + link)
8. Test locally, then push to GitHub

---

## Folder structure explained

```
between-versions/
├── index.html          ← Home page
├── essays.html         ← List of all essays
├── style.css           ← All the design (colors, fonts, layout)
├── README.md           ← What this blog is (on GitHub)
├── .gitignore          ← Files Git should ignore
└── essays/
    ├── essay-template.html   ← Copy this for every new essay
    ├── essay-001.html
    ├── essay-002.html
    └── ...
```

---

## Quick reference — Git commands

| What you want to do | Command |
|---|---|
| See what's changed | `git status` |
| Save a snapshot | `git add . && git commit -m "your message"` |
| Send to GitHub | `git push` |
| See your history | `git log --oneline` |

---

*You now know enough to keep this site alive indefinitely. The rest is just writing.*

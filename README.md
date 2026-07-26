# Marco Pilotti — Portfolio Site

One file: `index.html`. No build step, no dependencies. That's deliberate — fewer moving parts while you're learning Git.

---

## 1. Before you push: fix these two things

Open `index.html` and search for:

1. `https://www.linkedin.com/` — replace both occurrences with your actual LinkedIn URL.
2. `marco.pilotti96@gmail.com` — already correct, but double-check it's the address you want public.

Everything else (metrics, build log, skills) is real content pulled from your CV — but it's yours to edit any time. See section 4.

---

## 2. Learn Git + GitHub, step by step

You've never used GitHub, so here's the minimum you actually need — not the whole manual.

### Mental model first
- **Git** = version control tool running on your laptop. It tracks changes to files over time.
- **GitHub** = a website that hosts a copy of your Git project online, so others (and GitHub Pages) can see it.
- **Repository ("repo")** = a project folder that Git is tracking.
- **Commit** = a saved checkpoint of your work, with a message describing what changed.
- **Push** = upload your commits from your laptop to GitHub.

### Step 1 — Install Git & create a GitHub account
```bash
git --version
```
If that errors, install Git from git-scm.com. Then create a free account at github.com.

### Step 2 — Create the repo on GitHub
1. On github.com, click **New repository**.
2. Name it `portfolio` (or `your-username.github.io` — see the note in section 3 about the URL you get either way).
3. Keep it **Public**, don't add a README/gitignore (you already have files).
4. Click **Create repository**. GitHub shows you a page with setup commands — keep that tab open.

### Step 3 — Push this project to it
In your terminal, `cd` into this folder, then:
```bash
git init
git add .
git commit -m "feat: first version of portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git push -u origin main
```
Replace `YOUR_USERNAME` with your GitHub username. Git will ask you to authenticate — GitHub will prompt you to use a browser sign-in or a personal access token the first time.

### Step 4 — Turn on GitHub Pages (free hosting)
1. On your repo page, go to **Settings → Pages**.
2. Under "Build and deployment," set **Source** to `Deploy from a branch`.
3. Branch: `main`, folder: `/ (root)`. Save.
4. Wait ~1 minute, refresh — GitHub gives you a live URL.

### The URL you'll get
- Repo named `portfolio` → `https://YOUR_USERNAME.github.io/portfolio/`
- Repo named `YOUR_USERNAME.github.io` → `https://YOUR_USERNAME.github.io/` (cleaner, no `/portfolio/` at the end — worth using this name if you want the tidiest link to put on your CV/LinkedIn)

---

## 3. The everyday loop (this is 90% of what you'll ever do)

Every time you update content:
```bash
git add .
git commit -m "update: describe what changed"
git push
```
That's it. GitHub Pages redeploys automatically within a minute of a push to `main`.

---

## 4. Using Claude Code to keep building this

Open this folder in Claude Code and just describe changes in plain language, e.g.:
- "Add a new build-log entry: finished the Retake AI teardown, link it to [URL]"
- "Add a case-study section for the ASO analysis agent with a short writeup"
- "Swap the accent color to test a different look"

After Claude Code makes the change, review it, then run the `git add / commit / push` loop above. Each of those commits is itself a real, honest build-log entry — which is exactly what the "Build Log" section on the site is modeling.

**Content pillar idea:** once you've done this once, "how I built my portfolio with Claude Code, end to end" is a genuine post for LinkedIn or Substack — it's AI-native-workflow content that's also proof, not just a claim.

---

## 5. What to update as things progress

- [ ] Replace LinkedIn placeholder links
- [ ] Add a case study section once the Retake AI teardown is done (change its `wip` tag to `feat` in the build log, add a link)
- [ ] Same for the ASO analysis agent once it's running end-to-end
- [ ] Consider a custom domain later (GitHub Pages supports this under Settings → Pages → Custom domain) — not necessary now
- [ ] Add your CV as a downloadable PDF link once you're happy with a version

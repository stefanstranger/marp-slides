# 📊 marp-slides

> Marp presentations auto-built and published to GitHub Pages via GitHub Actions.

**Owner:** [@stefanstranger](https://github.com/stefanstranger)

---

## How it works

Every time you push to `main`, GitHub Actions:
1. Converts all `slides/*.md` files to HTML using [Marp](https://marp.app)
2. Generates an `index.html` listing all presentations
3. Deploys everything to the `gh-pages` branch
4. GitHub Pages serves it at `https://stefanstranger.github.io/marp-slides/`

---

## ✍️ Adding a new presentation

1. Create a new Markdown file in `slides/`:
   ```
   slides/my-new-talk.md
   ```

2. Add Marp front matter at the top:
   ```yaml
   ---
   marp: true
   theme: gaia
   paginate: true
   ---
   ```

3. Write your slides (separate them with `---`)

4. Push to `main`:
   ```bash
   git add slides/my-new-talk.md
   git commit -m "Add: my-new-talk presentation"
   git push
   ```

5. GitHub Actions builds and deploys automatically — usually done in ~60 seconds.

---

## 🚀 First-time setup (one-time steps)

### 1. Create the GitHub repository

```bash
# Create repo on GitHub (via CLI or web UI), then:
git remote add origin https://github.com/stefanstranger/marp-slides.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repo on GitHub → **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Branch: `gh-pages` / folder: `/ (root)`
4. Click **Save**

After the first Actions run, your slides will be live at:
```
https://stefanstranger.github.io/marp-slides/
```

### 3. (Optional) Allow GitHub Actions to push to gh-pages

GitHub Actions needs write access. By default it has it via `GITHUB_TOKEN`, but double-check:
- **Settings → Actions → General → Workflow permissions**
- Set to **Read and write permissions**

---

## 📁 Repository structure

```
marp-slides/
├── .github/
│   └── workflows/
│       └── marp.yml        ← Auto-build workflow (don't edit unless needed)
├── slides/
│   └── example.md          ← Example presentation (feel free to keep or delete)
├── .gitignore
└── README.md               ← You are here
```

---

## 🎨 Marp themes

Available built-in themes: `default`, `gaia`, `uncover`

Set in front matter:
```yaml
---
marp: true
theme: uncover
---
```

For custom themes, place a `.css` file in the repo and reference it with the `--theme` option in the workflow.

---

## Local preview (optional)

Marp CLI is available for local preview:

```bash
# Preview a single file in browser
marp --preview slides/example.md

# Convert to HTML locally
marp slides/example.md --output dist/example.html
```

Install: `npm install -g @marp-team/marp-cli`

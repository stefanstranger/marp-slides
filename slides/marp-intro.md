---
marp: true
theme: gaia
paginate: true
backgroundColor: #0f172a
color: #e2e8f0
style: |
  section {
    font-family: 'Segoe UI', Arial, sans-serif;
  }
  h1 { color: #38bdf8; }
  h2 { color: #7dd3fc; }
  h3 { color: #bae6fd; }
  code { background: #1e293b; color: #a5f3fc; border-radius: 4px; padding: 0.1em 0.4em; }
  pre { background: #1e293b; border-left: 4px solid #38bdf8; border-radius: 4px; }
  a { color: #38bdf8; }
  table { width: 100%; }
  th { background: #1e40af; color: white; }
  td { border-bottom: 1px solid #334155; }
  section.lead h1 { font-size: 2.4em; text-align: center; }
  section.lead p { text-align: center; color: #94a3b8; }
---

<!-- _class: lead -->

# 🎯 Marp
## Markdown → Beautiful Slides

Write in Markdown. Present anywhere.

> *[marp.app](https://marp.app) · Built with Marp itself*

---

# What is Marp?

**Marp** = Markdown Presentation Ecosystem

- ✍️ Write slides in plain **Markdown**
- 🎨 Export to **HTML**, **PDF**, or **PowerPoint**
- ⚡ No design skills needed — just focus on content
- 🔧 Works in **VS Code**, **CLI**, or **GitHub Actions**

```markdown
# My First Slide
Hello world!

---

# My Second Slide
It's that simple.
```

---

# Why Marp?

| Feature | Marp | PowerPoint | Google Slides |
|---|---|---|---|
| Version control | ✅ Git | ❌ | ❌ |
| Plain text | ✅ | ❌ | ❌ |
| Auto-publish CI/CD | ✅ | ❌ | ❌ |
| Free & open source | ✅ | ❌ | ✅ |
| Code highlighting | ✅ | ❌ | ❌ |

**Bottom line:** if you write Markdown, you already know Marp.

---

# Writing Slides

Split slides with `---`. Front matter controls everything:

```yaml
---
marp: true
theme: gaia        # default | gaia | uncover
paginate: true
backgroundColor: #0f172a
---
```

**Per-slide directives:**

```markdown
<!-- _class: lead -->        ← centered hero slide
<!-- _backgroundColor: red -->
<!-- _paginate: false -->
```

---

# Images & Backgrounds

```markdown
# Full background image
![bg](https://example.com/photo.jpg)

# Left-split layout
![bg left:40%](image.png)

# Inline image with size
![w:400px](logo.png)
```

![bg right:35%](https://marp.app/assets/marp.svg)

Great for **hero slides**, **product screenshots**, and **diagrams**.

---

# Code Slides

Marp supports syntax highlighting out of the box:

```powershell
# Azure + PowerShell — a natural fit
Connect-AzAccount | Out-Null
Get-AzVM -Status |
  Where-Object { $_.PowerState -eq 'VM running' } |
  Select-Object Name, Location |
  Format-Table -AutoSize
```

```python
# Or Python, Go, TypeScript — any language
def hello_marp():
    return "Slides from Markdown 🎉"
```

---

# Export Options

```bash
# HTML (self-contained, shareable)
marp slides.md -o output.html

# PDF (print-ready)
marp --pdf slides.md

# PowerPoint (for the boardroom)
marp --pptx slides.md

# Watch mode (live preview while editing)
marp --watch slides.md
```

One source file → multiple formats. Zero friction.

---

# Auto-Publish with GitHub Actions

Push `.md` → GitHub Actions builds HTML → live on GitHub Pages.

```yaml
# .github/workflows/marp.yml
- name: Build slides with Marp
  uses: marp-team/marp-action@v2
  with:
    source: slides/
    output: dist/

- name: Deploy to GitHub Pages
  uses: peaceiris/actions-gh-pages@v4
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: dist/
```

**Result:** `https://stefanstranger.github.io/marp-slides/` ✨

---

<!-- _class: lead -->

# Get Started

```bash
npm install -g @marp-team/marp-cli
marp --watch my-slides.md
```

📝 Write · 🚀 Push · 🌐 Publish

**[marp.app](https://marp.app) · [@stefanstranger](https://github.com/stefanstranger)**

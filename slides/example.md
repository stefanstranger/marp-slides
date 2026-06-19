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
  code { background: #1e293b; color: #a5f3fc; border-radius: 4px; padding: 0.1em 0.3em; }
  pre { background: #1e293b; border-left: 4px solid #38bdf8; }
  a { color: #38bdf8; }
---

# ☁️ My Azure & AI Toolkit
### Stefan Stranger — Cloud & AI Enthusiast

Building modern cloud solutions with Azure, PowerShell, and AI

> *github.com/stefanstranger*

---

## 🛠️ The Stack

Tools I reach for every day:

- **Azure** — the cloud backbone
- **PowerShell** — the Swiss Army knife for automation
- **Bicep / ARM** — infrastructure as code
- **GitHub Actions** — CI/CD that just works
- **Azure OpenAI** — bringing AI to enterprise workloads

---

## ⚡ PowerShell + Azure: A Love Story

```powershell
# Connect and get all running VMs in one line
Connect-AzAccount | Out-Null
Get-AzVM -Status |
  Where-Object { $_.PowerState -eq 'VM running' } |
  Select-Object Name, ResourceGroupName, Location |
  Format-Table -AutoSize
```

**Why PowerShell?**
- Cross-platform (Windows, Linux, macOS)
- First-class Azure SDK support
- Perfect for automation pipelines

---

## 🤖 AI-Augmented Development

Integrating Azure OpenAI into real workflows:

1. **Code review assistant** — AI-assisted PR summaries
2. **Log analysis** — Natural language over structured telemetry  
3. **IaC generation** — Describe infra, get Bicep back
4. **Documentation** — Auto-generate from code comments

```bash
# Even these slides were drafted with AI assistance! ✨
```

---

## 📢 Find Me Online

| Platform | Link |
|----------|------|
| 📝 Blog | [stefanstranger.github.io](https://stefanstranger.github.io) |
| 🐙 GitHub | [@stefanstranger](https://github.com/stefanstranger) |
| 🐦 Twitter/X | [@sstranger](https://twitter.com/sstranger) |

---

*Thanks for watching!*
*These slides were built with [Marp](https://marp.app) 🎉*

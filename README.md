# Jonas Becker — Personal Website

A personal website with a landing page, About Me, CV, Blog, and Contact pages.
Built with plain HTML, CSS, and vanilla JavaScript. No frameworks, no build step.

---

## 📁 File Structure

```
jonas-becker-website/
├── index.html          ← Landing page
├── about.html          ← About Me page
├── cv.html             ← CV / Résumé page
├── blog.html           ← Blog listing page
├── blog/
│   ├── post-1.html     ← Sample blog post (duplicate & edit for new posts)
│   ├── post-2.html
│   ├── post-3.html
│   └── post-4.html
├── contact.html        ← Contact page
├── css/
│   └── style.css       ← All styles
├── js/
│   └── main.js         ← Mobile nav + page fade-in
├── CNAME               ← Custom domain for GitHub Pages
└── README.md           ← This file
```

---

### Configure DNS at Your Domain Registrar
Log in to wherever you rented `jonas-becker.me` and go to the **DNS settings**.

Add these **A records** (they point your domain to GitHub's servers):

| Type | Name | Value            |
|------|------|-----------------|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |

Also add this **CNAME record** (for `www`):

| Type  | Name | Value                        |
|-------|------|------------------------------|
| CNAME | www  | YOUR-USERNAME.github.io      |

> DNS changes can take up to 24–48 hours to propagate, but usually happen within minutes.

### Enable HTTPS (Recommended)
1. Go back to **GitHub → Settings → Pages**
2. Once DNS is verified, check **Enforce HTTPS**
3. Your site will be available at `https://jonas-becker.me` 🎉

```bash
# Edit any files, then:
git add .
git commit -m "Update about page"
git push
```
GitHub Pages will automatically rebuild and deploy your site within a minute or two.

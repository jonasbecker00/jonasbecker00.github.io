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

## 🚀 Step-by-Step: Publishing to GitHub Pages with a Custom Domain

### Step 1 — Create a GitHub Account (if you don't have one)
Go to https://github.com and sign up for a free account.

### Step 2 — Create a New Repository
1. Click the **+** icon (top-right) → **New repository**
2. Name it exactly: `YOUR-USERNAME.github.io`
   - Example: if your username is `jonas-becker`, name it `jonas-becker.github.io`
3. Set it to **Public**
4. Do **not** initialize with a README (you already have one)
5. Click **Create repository**

### Step 3 — Upload the Website Files
**Option A — via the GitHub website (easiest):**
1. Open your new repository on GitHub
2. Click **Add file** → **Upload files**
3. Drag and drop ALL the files and folders from this project
4. Click **Commit changes**

**Option B — via Git (recommended for future updates):**
```bash
# Install Git if needed: https://git-scm.com
cd path/to/jonas-becker-website

git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
git push -u origin main
```

### Step 4 — Enable GitHub Pages
1. In your repository, go to **Settings** (top tab)
2. In the left sidebar, click **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Choose branch: **main** and folder: **/ (root)**
5. Click **Save**

GitHub will show you a URL like `https://your-username.github.io` — your site is now live!

### Step 5 — Connect Your Custom Domain `jonas-becker.me`

#### 5a — Add the Domain in GitHub
1. Still in **Settings → Pages**
2. Under **Custom domain**, type `jonas-becker.me`
3. Click **Save**
4. GitHub will check for a CNAME record (the `CNAME` file is already in your repo ✓)

#### 5b — Configure DNS at Your Domain Registrar
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

#### 5c — Enable HTTPS (Recommended)
1. Go back to **GitHub → Settings → Pages**
2. Once DNS is verified, check **Enforce HTTPS**
3. Your site will be available at `https://jonas-becker.me` 🎉

---

## ✏️ How to Customize the Content

### Replace Lorem Ipsum text
Open any `.html` file in a text editor and replace the placeholder text with your own.

### Add your photo
- Save your photo as `images/photo.jpg`
- In `about.html`, replace the placeholder `<div class="about-photo">` with:
  ```html
  <img src="images/photo.jpg" alt="Jonas Becker" class="about-photo" style="object-fit:cover;">
  ```

### Add a new blog post
1. Duplicate `blog/post-1.html` and rename it (e.g. `post-5.html`)
2. Edit the title, date, and body text
3. In `blog.html`, add a new `<a class="blog-card">` entry pointing to your new file

### Change colors or fonts
All visual variables are at the top of `css/style.css`:
```css
:root {
  --bg:       #f7f4ef;   /* page background */
  --accent:   #c8602a;   /* terracotta highlight */
  --accent2:  #4a7c59;   /* sage green */
  /* ... */
}
```

### Make the contact form work
The form currently does nothing on submit. To receive emails:
1. Sign up at https://formspree.io (free tier available)
2. Create a new form and get your endpoint URL
3. In `contact.html`, change `action="#"` to your Formspree endpoint:
   ```html
   <form action="https://formspree.io/f/YOUR-ID" method="post">
   ```

---

## 🛠 Making Future Updates

After the initial setup, updating the site is simple:

```bash
# Edit any files, then:
git add .
git commit -m "Update about page"
git push
```
GitHub Pages will automatically rebuild and deploy your site within a minute or two.

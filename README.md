# Md Yasir Arafat — Personal Research Website

A complete, static academic personal website deployable directly to **GitHub Pages**.

## 🚀 Quick Deploy to GitHub Pages

### Option A — Upload Directly (Simplest)

1. Create a new GitHub repository named `yourusername.github.io`  
   (replace `yourusername` with your actual GitHub username)
2. Upload `index.html` to the root of the repository
3. Go to **Settings → Pages → Source → Deploy from a branch → main / root**
4. Your site will be live at `https://yourusername.github.io` within a minute

### Option B — GitHub Actions (Recommended)

1. Create a repository named `yourusername.github.io`
2. Push `index.html` to the `main` branch
3. Create `.github/workflows/deploy.yml` with the content below

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: actions/checkout@v4
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
```

## 📁 File Structure

```
yourusername.github.io/
├── index.html          ← Complete website (single file)
├── README.md
└── assets/             ← Add your photo here (optional)
    └── profile.jpg
```

## ✏️ Personalisation Checklist

### Essential Updates

- [ ] **Profile photo**: Replace the placeholder in the hero section.  
      In `index.html`, find `<div class="hero-photo-placeholder">` and replace with:
      ```html
      <img src="assets/profile.jpg" alt="Md Yasir Arafat" style="width:100%;height:100%;object-fit:cover;">
      ```

- [ ] **CV download link**: Find `onclick="alert('Replace with link to your CV PDF')"` and replace with:
      ```html
      href="assets/cv.pdf"
      ```

- [ ] **Contact form**: The contact form currently shows a placeholder alert.  
      Set up [Formspree](https://formspree.io) (free) and replace the form action.

- [ ] **Google Scholar**: Add your Google Scholar profile link in the contact section

- [ ] **ORCID / LinkedIn**: Add these links to the contact section if desired

### Optional Enhancements

- Add a `favicon.ico` in the root folder
- Add Open Graph image (`og-image.png`) for social sharing preview
- Add Google Analytics by inserting the GA script before `</head>`

## 🎨 Design Tokens (easy to customise)

All colours are CSS variables at the top of `index.html`:

```css
--blue: #1a4fad;        /* primary blue */
--accent: #0ea5e9;      /* highlight blue */
--ink: #0f1923;         /* body text */
--ink-soft: #3a4a5c;    /* secondary text */
```

## 📞 Contact

Md Yasir Arafat  
Assistant Professor, CSE  
Jashore University of Science and Technology  
arafatcse@just.edu.bd

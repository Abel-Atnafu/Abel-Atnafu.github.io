# Portfolio Handoff — Abel Atnafu

> **Live site:** https://abel-atnafu.github.io  
> **Branch:** `main` (auto-deployed via GitHub Pages)

---

## What's in the Repo

| File | Description |
|------|-------------|
| `index.html` | Main portfolio — single-page, vanilla HTML/CSS/JS |
| `index3.html` | "One Man Success" gold mining page (separate project) |
| `resume.pdf` | Abel's resume |
| `README.md` | Repo description |

---

## Portfolio Structure (`index.html`)

The portfolio is a single HTML file with embedded CSS and JS — no build step, no dependencies.

### Sections

| ID | Label | What to edit |
|----|-------|--------------|
| `#home` | Hero | Name, tagline, description |
| `#about` | About | Bio text, info cards |
| `#skills` | Skills | `data-percent` attributes + skill names |
| `#projects` | Projects | Project cards |
| `#journey` | Journey | Timeline items |
| `#contact` | Contact | Email, GitHub, LinkedIn links |

### Design System (CSS variables at top of `<style>`)

```css
--bg: #060b18          /* Page background */
--surface: #0c1225     /* Card background */
--blue: #3b82f6        /* Primary accent */
--cyan: #06d6d6        /* Secondary accent */
--indigo: #6366f1      /* Tertiary accent */
--text: #e4eaf5        /* Body text */
--muted: #6880a8       /* Subdued text */
```

To change the color scheme, update these variables — everything cascades from them.

---

## How to Update Each Section

### Hero Text (line ~751)
```html
<h1>I build things<br />for the <span class="gradient-text">web.</span></h1>
<p>Your description here...</p>
```

### Skills (line ~821)
Adjust `data-percent="90"` and the `<span class="sb-name">` text:
```html
<div class="skill-bar-item" data-percent="90">
  <div class="sb-header">
    <span class="sb-name">HTML & CSS</span>
    <span class="sb-percent">90%</span>
  </div>
  ...
</div>
```

### Projects (line ~898)
Add/edit project cards inside `.projects-grid`:
```html
<div class="project-card">
  <div class="p-number">02</div>
  <h3>Project Name</h3>
  <p>Description...</p>
  <div class="tags">
    <span class="tag-pill">Python</span>
  </div>
</div>
```
Add `class="featured"` to the first card to make it span full width.

### Contact Links (line ~984)
```html
<a href="mailto:abelatnafu.g@gmail.com" class="contact-card">...</a>
<a href="https://github.com/Abel-Atnafu" class="contact-card">...</a>
```

### Resume Link (line ~1000 area)
Search for `resume.pdf` and update the `href`.

---

## Known Issues to Fix

| Line | Issue | Fix |
|------|-------|-----|
| ~762 | `"Ethipai"` → should be `"Ethiopia"` | Typo in hero paragraph |
| ~762 | `"Phython"` → should be `"Python"` | Typo in hero paragraph |
| ~762 | `"bekive greate"` → should be `"believe great"` | Typo in hero paragraph |
| ~985 | `href="mailto:your@email.com"` → placeholder not updated | Change to actual email |

---

## Deployment

The site deploys automatically via GitHub Pages from the `main` branch.

**Workflow:**
1. Edit files locally or directly on GitHub
2. Commit to `main`
3. GitHub Pages rebuilds in ~30 seconds
4. Changes live at https://abel-atnafu.github.io

**No build step required** — it's plain HTML.

---

## Local Preview

No server needed for basic edits. Just open `index.html` in a browser:

```bash
# Mac/Linux
open index.html

# Or use a simple local server (recommended for accurate preview)
python3 -m http.server 8080
# then visit http://localhost:8080
```

---

## Animations

Scroll-triggered reveals use an `IntersectionObserver` at the bottom of `index.html`. Elements with class `reveal` fade in when they enter the viewport. The skill bars animate their width via `data-percent` on scroll.

---

## Next Steps / Ideas

- [ ] Fix the 3 typos in the hero paragraph (see Known Issues above)
- [ ] Add real GitHub/LinkedIn links to the contact section
- [ ] Add more projects as they're built
- [ ] Add a project link/demo URL to each project card
- [ ] Update resume.pdf when a new version is ready
- [ ] Add Open Graph meta tags for better link previews on social media

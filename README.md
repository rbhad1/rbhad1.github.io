# Portfolio Template — Fill-In Guide

## File structure

```
portfolio-site/
├── index.html              ← assembles everything together — you won't edit this much
├── styles.css               ← all colors, fonts, spacing
└── sections/
    ├── nav.html              ← top navigation bar
    ├── hero.html             ← name + intro banner
    ├── about.html            ← About Me
    ├── experience.html       ← work history / timeline
    ├── projects.html         ← project cards
    ├── contact.html          ← contact links
    └── footer.html           ← bottom footer
```

Each section is its own small file, so you can open just `sections/experience.html` to edit your work history without scrolling past everything else.

## ⚠️ Important: you must run a local server to preview this

`index.html` pulls each section in using JavaScript (`fetch`). Browsers block that when you just double-click an HTML file (it treats it as a security risk). So instead of double-clicking `index.html`, do one of the following:

**Option A — Python (already installed on most Macs/Linux, and on Windows if you have Python)**
1. Open a terminal in the `portfolio-site` folder
2. Run:
   ```
   python3 -m http.server 8000
   ```
   (Windows may need `python` instead of `python3`)
3. Open `http://localhost:8000` in your browser

**Option B — VS Code "Live Server" extension**
1. Install the "Live Server" extension in VS Code
2. Open the `portfolio-site` folder in VS Code
3. Right-click `index.html` → "Open with Live Server"

**Option C — Node.js**
```
npx serve .
```
then open the URL it gives you.

This local-server step is only for *previewing while you edit*. Once you're ready to actually publish the site (e.g. GitHub Pages, Netlify, Vercel), it'll work automatically — real hosting always serves files over http, so `fetch` works fine there without any extra steps.

## What to fill out, file by file

**sections/hero.html**
- `<h1>Your Name</h1>`
- The `<p>` below it: your degree/field, school, one-line pitch
- "Download CV" link `href="#"` → path to your resume PDF, e.g. `href="resume.pdf"`
- LinkedIn / GitHub / Email links in `.social-row`
- `.hero-photo` box → replace with `<img src="photo.jpg" alt="Your Name">`

**sections/nav.html**
- `<div class="logo">YN.</div>` → your initials

**sections/about.html**
- `.about-photo` box → replace with a second `<img>`, or delete the div
- The three `<p>` tags → your bio
- "Download Resume" link → same PDF path as above

**sections/experience.html**
Each `.job` block is one role. Copy/paste the block to add more, delete to remove.
- 📍 location, 📅 dates
- Job title, company name
- Summary + bullet list of achievements
- `.tags` → skills/tools used (one `<span class="tag">` per skill)

**sections/projects.html**
Each `.card` is one project. Copy/paste to add more.
- Project name, description
- `.tags` → tech stack
- `.card-links` → Code/Live/Paper links (delete the ones you don't need)

**sections/contact.html**
Update the `mailto:`, LinkedIn, and GitHub links.

**sections/footer.html**
Update the name and year.

## Adding real photos

Put image files in the `portfolio-site` folder (or an `images/` subfolder), then replace the placeholder `<div class="hero-photo">Your Photo</div>` with:

```html
<img src="photo.jpg" alt="Your Name" style="border-radius:16px; aspect-ratio:1/1; object-fit:cover;">
```

## Changing colors/fonts

At the top of `styles.css` there's a `:root` block with all the color and font variables (`--accent`, `--bg`, `--font-display`, etc.) — change values there and it updates the whole site.

# Lorven Interio — Website

A classy, light-blue themed website for **Lorven Interio** ("You Dream We Design"), a premium interior design studio.

## What's inside
- `index.html` — full one-page site: Hero, About, Services, Gallery (images + YouTube video), scrolling "Prestigious Projects" marquee, Contact Us
- `css/style.css` — design system (colors, type, layout, responsive rules)
- `js/script.js` — mobile nav, gallery lightbox, contact form handling
- `assets/logo.png` — your Lorven Interio logo (background removed)
- `assets/img/*.svg` — original gallery artwork (living room, bedroom, kitchen, home office, dining room, foyer)

## Running locally
No build step needed — it's plain HTML/CSS/JS. Just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Deploying with GitHub + Netlify

1. Create a new repo on GitHub (e.g. `lorven-interio-website`).
2. In this folder, run:
   ```bash
   git init
   git add .
   git commit -m "Initial site: Lorven Interio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/lorven-interio-website.git
   git push -u origin main
   ```
3. On [Netlify](https://app.netlify.com):
   - **Add new site → Import an existing project → GitHub**
   - Select your repo
   - Build command: *(leave blank)*
   - Publish directory: `.`
   - Click **Deploy**

That's it — Netlify will auto-deploy on every push to `main`.

## Customizing

- **Contact info**: search for `Srinath` and `9246167171` in `index.html` to update.
- **YouTube videos**: add more `<div class="video-card">` blocks inside `#videoGrid` in `index.html`, following the existing pattern — just swap the embed URL (`https://www.youtube.com/embed/VIDEO_ID`).
- **Gallery images**: replace the SVGs in `assets/img/` with real project photos (JPG/PNG) once available — just keep the same filenames or update the `src` attributes in `index.html`.
- **Projects marquee**: edit the text inside `.marquee-content` in `index.html` (there are two identical blocks for the seamless loop — keep them in sync).
- **Contact form**: currently shows a confirmation message client-side only. Wire it up to a form backend (e.g. Netlify Forms, Formspree) when ready to receive real enquiries.

## Netlify Forms (optional, recommended)

To let Netlify capture form submissions with zero backend:
1. Add `data-netlify="true"` and a hidden `name="contact"` input to the `<form>` tag in `index.html`.
2. Redeploy — submissions will appear in your Netlify dashboard under **Forms**.

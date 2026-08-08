# Witty Foundry — Landing Page

A single static HTML file (Tailwind via CDN + vanilla JS). No build step required.

## Deploy to Vercel

**Option A — Vercel CLI**
1. Open a terminal in this folder.
2. Run: `npx vercel`
3. Follow the prompts (link/create a project). Accept the defaults — no framework, no build command, output directory is the project root.
4. Run `npx vercel --prod` to deploy to production.

**Option B — Vercel dashboard (no CLI)**
1. Push this folder to a GitHub repo (or drag-and-drop the folder at vercel.com/new — Vercel supports direct folder upload).
2. In the Vercel dashboard, "Add New Project" → import the repo.
3. Framework preset: "Other" / static — leave build command and output directory blank.
4. Deploy.

## Google Form

The contact form is wired up to a live Google Form (`1FAIpQLSdq76LElg8AFDDw3eVYKQzfvZlUZBe6e4QK2-f2_ll6kdXFHA`) with all 7 fields mapped to their real `entry.xxxxxxx` IDs: Full name, School name, Email, Phone, Country, "I am a...", and the optional notes field. No further setup needed unless you change the Google Form's questions — if you do, you'll need to regenerate a pre-filled link and update the matching `entry.xxxxxxx` values in `index.html`.

## Files

- `index.html` — the entire site (markup, styles, and script in one file)
- `vercel.json` — minimal static-site config (clean URLs)

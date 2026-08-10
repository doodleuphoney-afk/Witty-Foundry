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

The contact form posts to a live Google Form (`1FAIpQLSdq76LElg8AFDDw3eVYKQzfvZlUZBe6e4QK2-f2_ll6kdXFHA`). Current field mapping:

| Question | `name` attribute |
| --- | --- |
| Full Name | `entry.1373030889` |
| School Name | `entry.539050985` |
| Email | `entry.1848182346` |
| Phone | `entry.1215452919` |
| Country | `entry.885935966` |
| I am a... | `entry.936102683` |
| Anything we should know? | `entry.366546603` |

The "I am a..." `<option value="...">` strings must match the Google Form's choices **exactly** (`School Owner`, `Administrator`, `Teacher`, `Parent`) — an unrecognised choice makes Google reject the entire response.

If you change the form's questions, re-read the authoritative IDs from the live form rather than guessing:

```bash
curl -sL "https://docs.google.com/forms/d/e/<FORM_ID>/viewform" | grep -o 'FB_PUBLIC_LOAD_DATA_ = .*'
```

Each question appears as `[<questionId>,"<Title>",null,<type>,[[<entryId>,...`  — the `entryId` is what goes into `name="entry.<entryId>"`.

## Files

- `index.html` — the entire site (markup, styles, and script in one file)
- `vercel.json` — minimal static-site config (clean URLs)

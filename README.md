# The Ledger — Deploy Package

This folder is a ready-to-publish static site: 5 HTML pages + 1 stylesheet, no build step required.

## Files
- `index.html` — homepage
- `methodology.html` — trust/disclosure page
- `review-betmgm.html`, `review-caesars.html`, `review-draftkings.html`, `review-hardrock.html` — operator reviews
- `review-template.html` — blank template for future operator reviews
- `guide-welcome-bonuses.html` — evergreen guide article
- `style.css` — shared stylesheet
- `content-plan.md`, `publishing-guide.md` — reference docs, not part of the live site

---

## How to deploy this with Claude Code

**Prerequisite (you do this once, yourself):** create a free account at
https://app.netlify.com and make sure you're logged in in your browser or via
`netlify login` in your terminal — Claude Code can't create the account or log in for you,
but once you're authenticated it can run everything below.

### Step 1 — Give Claude Code this folder
Unzip `the-ledger-site.zip` into a project folder, then open that folder in Claude Code
(or point Claude Code at the path).

### Step 2 — Commands to hand to Claude Code

If you want a GitHub-connected deploy (recommended — enables auto-redeploy on future edits):

```
git init
git add .
git commit -m "Initial site: homepage, 4 operator reviews, methodology, guide"
gh repo create the-ledger-nj --public --source=. --push
netlify init
```
`netlify init` will prompt to either link an existing Netlify site or create a new one —
choose "create a new site," pick your team, and accept the defaults (no build command,
publish directory `.`).

If you just want it live immediately with no GitHub repo (simplest):

```
netlify login
netlify deploy --prod --dir=.
```
This uploads the folder directly and gives you a live `https://your-site-name.netlify.app`
URL in the terminal output.

### Step 3 — Connect your own domain (optional, do in the Netlify dashboard)
Once live, go to Site settings → Domain management → Add a custom domain, and follow the
DNS instructions Netlify gives you. This part is easiest done by you directly in the
dashboard rather than via CLI.

### Step 4 — Before it's truly live for real users
Every `[bracketed placeholder]` still in the review pages — payout speed, game library
detail, your own rating — needs to be filled in from real testing before this should be
treated as a genuine public review site. The site is structurally ready to deploy now;
the content is a first honest draft, not a finished product.

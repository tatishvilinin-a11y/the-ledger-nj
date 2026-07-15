# Publishing Your Site — Step-by-Step (Netlify)

Netlify is the easiest path for a static HTML/CSS site like this one: free tier, drag-and-drop
deploy, automatic SSL, and a real custom domain in under 20 minutes.

## Option A — Drag and drop (fastest, no account setup for git)

1. Go to **https://app.netlify.com/** and sign up (email, or GitHub/Google login).
2. Once logged in, you'll land on your team's dashboard. Look for the box that says
   **"Drag and drop your site output folder here."**
3. On your computer, put these five files together in one folder:
   `index.html`, `review-template.html`, `guide-welcome-bonuses.html`, `methodology.html`, `style.css`
4. Drag that whole folder onto the Netlify dashboard box.
5. Netlify uploads it and gives you a live URL immediately, like `random-name-123.netlify.app`.
   Your site is now genuinely live on the internet — this step alone is enough to test everything works.

## Option B — Connect a GitHub repo (better long-term — enables auto-updates)

Worth doing once you're past the first draft, since every future edit auto-publishes.

1. Create a free GitHub account at **https://github.com** if you don't have one.
2. Create a new repository (e.g. `the-ledger-nj`), and upload the five site files to it
   (GitHub's web UI has an "Add file → Upload files" button — no command line needed).
3. In Netlify, click **"Add new site" → "Import an existing project"**, choose GitHub, and
   authorize access.
4. Select your repository. Leave the build settings blank (no build command needed — it's
   plain HTML) and set the publish directory to `/` (the repo root).
5. Click **Deploy site**. From now on, any change you push to GitHub automatically redeploys
   the live site within a minute or two.

## Connecting your own domain

1. Buy a domain if you haven't — Namecheap, Cloudflare Registrar, or Google Domains successor
   (~$10–15/year for a `.com`).
2. In Netlify, go to **Site settings → Domain management → Add a custom domain**, and enter
   your domain.
3. Netlify shows you the DNS records to add. Two common approaches:
   - **Easiest**: point your domain's nameservers to Netlify's (Netlify walks you through this
     in the same screen) — Netlify then manages all DNS for you.
   - **Alternative**: keep your current DNS provider and just add the specific A record / CNAME
     Netlify gives you.
4. DNS changes can take anywhere from a few minutes to a few hours to propagate. Netlify auto-
   issues a free SSL certificate (via Let's Encrypt) once it detects the domain is pointed
   correctly — your site will show the padlock/https automatically, no extra steps.

## After it's live

1. **Google Search Console** (search.google.com/search-console) — verify ownership of your
   domain (Netlify's DNS panel makes this a one-click TXT record add), then submit your site
   so Google starts crawling it.
2. **robots.txt and sitemap** — for a 5-page site you can skip a generated sitemap tool and just
   create a plain `sitemap.xml` listing your pages, or install a free tool later once you have
   more pages (most SEO plugins/generators can do this once you move to a CMS).
3. **Analytics** — add Plausible (privacy-friendly, paid) or Google Analytics 4 (free) by
   pasting their tracking snippet into the `<head>` of each HTML file.
4. **Before going live for real**: make sure every bracketed placeholder in your review pages
   and the methodology page is filled with real, current, verified information — see the
   earlier checklist. A half-finished template with placeholder text is a bad first impression
   for both users and Google.

## A note on scaling past 5 pages
Once you're publishing 20–30+ operator reviews and guides, hand-editing raw HTML files gets
tedious fast. At that point it's worth moving to a lightweight static site generator (Astro,
Eleventy, or Hugo) or a simple headless CMS — but there's no need to make that jump before you
have real content and real traffic validating the approach.

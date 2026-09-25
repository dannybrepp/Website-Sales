# Small Business Website Template

A single-file, self-contained website template (HTML + CSS + JS, no build step, no dependencies besides Google Fonts). Built around a fictional coffee shop ("Ember & Oak") so it reads like a real site instead of empty boxes — swap the content and it becomes any local business: salon, gym, tutor, contractor, restaurant, whatever your client needs.

## What's in it

One page with these sections, in order: sticky nav → hero → about → services/menu → gallery → testimonials → hours/contact form → footer. This structure covers ~90% of small business site requests. Delete or duplicate sections as needed.

## How to reskin it for a real client (in order)

1. **Colors** — open `index.html`, find the `:root { ... }` block near the top of the `<style>` section. Change the six variables there (`--bg`, `--bg-deep`, `--ink`, `--ochre`, `--rust`, `--line`) and the whole site's palette updates. Pick colors from the client's logo or industry, not defaults.
2. **Fonts** — the `<link>` tag near the top pulls two Google Fonts (Fraunces for headings, Work Sans for body). Swap the font names in both the `<link>` href and the `font-family` values in CSS if the client's brand calls for something different. fonts.google.com has free options for any tone (playful, corporate, elegant, etc).
3. **Text** — replace every piece of copy: business name (`.brand`, `<title>`, footer), the hero headline and paragraph, the about section, the four menu/service rows, the three testimonials, and the hours/address/phone block.
4. **Images** — replace every `<img src="...">`. The template uses free Unsplash placeholder images; swap in the client's real photos (or new stock photos matching their industry) at the same URLs, or point to local image files if you're hosting the images yourself.
5. **Contact form** — right now the form just shows an alert on submit. Before it goes live, connect it to something real:
   - Easiest: use [Formspree](https://formspree.io) (free tier works) — replace the `onsubmit` attribute with a real `action="https://formspree.io/f/yourFormID"` and remove the `onsubmit`.
   - Or: use a simple `mailto:` link instead of a form if the client just wants a phone/email, no backend needed.
6. **Sections** — for a business with no "menu" (e.g. a plumber or tutor), rename that section to "Services" and adjust the row content (the price column can just say "Starting at $X" or be removed).

## How to put this on GitHub (step by step)

You said you're already on GitHub — here's the exact path from here to a live URL.

1. **Create a new repository**
   - On github.com, click the **+** in the top right → **New repository**.
   - Name it something like `client-name-website` (or `my-portfolio-template` if this is just for you right now).
   - Keep it **Public** (required for the free GitHub Pages hosting below).
   - Don't initialize with a README (you already have one) — or do, and just overwrite it.

2. **Upload the files**
   - Easiest way if you're not comfortable with git commands yet: on the new repo's page, click **Add file → Upload files**, then drag in `index.html` and `README.md`. Commit directly to the `main` branch.
   - If you do want to use git from your computer instead:
     ```bash
     git init
     git add index.html README.md
     git commit -m "Initial website template"
     git branch -M main
     git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
     git push -u origin main
     ```

3. **Turn on GitHub Pages (this makes it a live website, for free)**
   - In your repo, go to **Settings → Pages** (left sidebar).
   - Under "Build and deployment," set **Source** to **Deploy from a branch**.
   - Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
   - Wait about 1-2 minutes. Refresh the Pages settings screen — you'll see a green box with your live URL, something like:
     `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

4. **Every time you edit the site later**
   - Edit `index.html`, then either re-upload it through the GitHub website (Add file → Upload files, overwrite) or, if using git:
     ```bash
     git add index.html
     git commit -m "Update site content"
     git push
     ```
   - GitHub Pages auto-redeploys within a minute or two of any push to `main`.

5. **Optional: use a real domain later**
   - Once a client wants `theirbusiness.com` instead of the github.io URL, buy the domain (Namecheap, Google Domains, etc — $10-15/year) and add a `CNAME` file pointing to it. GitHub's Pages docs walk through this ("custom domain") when you're ready — not needed for your first few practice projects.

## Reusing this as your template going forward

Keep this repo as your **master template** — don't build directly into it for a real client. Instead, for each new project:
- Click **Use this template** on the repo page (GitHub has a built-in "Template repository" setting — turn it on under Settings → General → Template repository), which creates a fresh copy for each new client without touching your master file.
- Or just download the files and start a brand-new repo per client.

This way every new project starts from your best version instead of from scratch, and you can keep improving the master template as you learn what clients actually ask for.

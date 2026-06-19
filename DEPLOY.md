# Launching your portfolio with a content dashboard

This sets up your site so you can **swap videos, edit films, and publish them live**
from a simple dashboard — no code, no waiting on anyone. It's free.

**How it works:** your films live in one file, `content/site.json`. A dashboard
(Decap CMS) lets you edit that file from your browser. Every time you hit
**Publish**, it saves to GitHub, and Netlify rebuilds your live site within a
minute. That's the whole loop.

```
You edit in the dashboard  →  saves to GitHub  →  Netlify republishes  →  live
```

---

## What's in this folder

```
index.html          ← your site (the portfolio itself)
support.js          ← required by index.html (keep it alongside)
content/site.json   ← YOUR FILMS — this is what the dashboard edits
admin/index.html    ← the editing dashboard
admin/config.yml    ← dashboard settings
```

---

## One-time setup (about 15 minutes)

### 1. Put the files on GitHub
1. Create a free account at [github.com](https://github.com).
2. New repository → name it e.g. `portfolio` → **Public** (or Private, both work) → Create.
3. Upload **all** the files in this folder, keeping the folder structure
   (`content/` and `admin/` stay as folders). Drag-and-drop works on github.com
   via "Add file → Upload files". Commit.

### 2. Connect it to Netlify
1. Sign up free at [netlify.com](https://app.netlify.com) — choose "Log in with GitHub".
2. **Add new site → Import an existing project → GitHub →** pick your `portfolio` repo.
3. Leave build settings blank (no build command, publish directory = `/` or empty). Deploy.
4. In ~30 seconds you get a live URL like `random-name.netlify.app`. That's your site.

### 3. Turn on the editing dashboard (DecapBridge)
> Netlify retired its old "Identity + Git Gateway" feature in 2025, so we use
> **DecapBridge** instead — a free service that does the same two jobs: logs you
> in, and lets the dashboard save to your GitHub repo. (It's missing from Netlify
> because Netlify removed it — nothing wrong on your end.)

1. Go to **[decapbridge.com](https://decapbridge.com)** and sign up (free).
2. **Add a site** → connect your GitHub repo (`portfolio`) when prompted.
3. It gives you four lines (repo, branch, identity_url, gateway_url). Open
   `admin/config.yml`, and **paste them over the placeholders** at the top —
   replace `YOUR-GITHUB-USERNAME/YOUR-REPO` and `YOUR-SITE-ID`. Commit the change
   to GitHub.
4. DecapBridge lets you **invite yourself by email** and set a password — that's
   your dashboard login.

### 4. Edit!
Go to **`your-site.netlify.app/admin/`**, log in, and you'll see your films.
Change a video link, reorder, rename a category, hit **Publish**. Wait ~1 min,
refresh your live site — done.

---

## Point your Namecheap domain at it
1. Netlify → **Domain management → Add a domain →** type your domain → confirm.
2. Netlify shows you DNS records. Easiest path:
   - In **Namecheap → Domain List → Manage → Nameservers**, choose **Custom DNS**
     and paste in Netlify's nameservers (Netlify shows them, e.g. `dns1.p0X.nsone.net`…).
   - Save. DNS propagates in anywhere from minutes to a few hours.
3. Back in Netlify, it auto-issues a free HTTPS certificate. Your site is now at your domain.

*(Alternative if you'd rather keep Namecheap's nameservers: add the A record and
CNAME Netlify lists, instead of switching nameservers.)*

---

## Day-to-day: how you change films
- **Just go to `your-domain.com/admin/`**, edit, Publish. That's it.
- The site visitors see always reflects `content/site.json` — the published file.
- You do **not** need this dashboard to view the site; it's only for editing.

## Notes
- **Videos:** paste YouTube, Vimeo, or direct `.mp4` links. The CMS doesn't host
  video files — keep big files on YouTube/Vimeo (free) and link them.
- **The private Edit/Admin mode built into the site** (visit `?admin`) still works
  for quick local previewing on your own browser, but those tweaks stay on your
  device. To change what **everyone** sees, use the `/admin/` dashboard — that's
  the one that publishes.
- **Posters:** optional. Leave the poster field blank and the tile shows a gradient.

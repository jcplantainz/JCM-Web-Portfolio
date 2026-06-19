# ✅ Start here

Everything is ready. You only have to do the account setup — no editing needed.

**The 4 steps (full details in DEPLOY.md):**

1. **GitHub** — create a free repo, drag ALL the contents of this folder into it
   (keep the `content/`, `admin/`, `media/` folders intact). Commit.
2. **Netlify** — "Import an existing project" → pick that repo → Deploy. No build
   settings to change. You get a live URL.
3. **Dashboard** — sign up free at [decapbridge.com](https://decapbridge.com),
   add your repo, and it gives you 4 config lines. Paste them into
   `admin/config.yml` (over the placeholders), commit, then invite yourself by
   email and set a password. *(This replaces Netlify's old "Identity" feature,
   which Netlify removed in 2025 — that's why you couldn't find it.)*
4. **Domain** — Netlify → Domain management → add your Namecheap domain, follow
   its DNS instructions.

Then edit films anytime at **your-domain.com/admin/** → Publish → live in ~1 min.

---

**Folder contents (don't rename or move these):**

- `index.html` + `support.js` — your site
- `content/site.json` — your films (what the dashboard edits)
- `admin/` — the editing dashboard
- `media/` — where dashboard image uploads land
- `netlify.toml` — Netlify config (leave as-is)
- `DEPLOY.md` — the full walkthrough

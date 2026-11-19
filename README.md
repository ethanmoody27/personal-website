# Personal Website

A plain HTML/CSS static site with no build step. It's hosted on Vercel and deploys automatically on every push to GitHub.

## Files

- `index.html` — all page content (search for "Your Name" and the placeholder text)
- `styles.css` — colors and layout (change `--accent` in `:root` to set your color)
- `favicon.svg` — the browser tab icon (change the "YN" initials)

## Preview locally

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321.

## Deploy (one-time setup)

1. **Push to GitHub**
   ```bash
   gh repo create personal-website --public --source=. --push
   ```
2. **Connect Vercel:** sign up at https://vercel.com with your GitHub account → *Add New → Project* → import `personal-website` → leave every setting at its default (Framework: "Other", no build command) → *Deploy*.
3. You'll get a URL like `personal-website-xyz.vercel.app`. From now on, each `git push` redeploys the site.

## Custom domain (optional)

1. Buy a domain (Cloudflare Registrar, Porkbun, or Namecheap, about $10–15/yr).
2. In Vercel: *Project → Settings → Domains* → add your domain.
3. Add the DNS records Vercel shows you at your registrar. HTTPS is set up automatically.

## Adding a backend later

For a contact form, comments, and so on:
- Add files under `api/` (for example `api/contact.js`). Vercel turns each one into a serverless function at `/api/contact`.
- Use [Supabase](https://supabase.com) for the database. Store its keys in *Vercel → Settings → Environment Variables*, never in the code.

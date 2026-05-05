# idejasildymui.lt — IdeaTherm Website

Production-ready Astro one-pager for **UAB „IdeaTherm"** — Lithuanian heating solutions company (vandens šildytuvai, momentiniai vandens šildytuvai, boileriai).

## Tech Stack

- **[Astro](https://astro.build/)** — static site generator (zero JS by default)
- **[Decap CMS](https://decapcms.org/)** — Git-based browser CMS
- **[Netlify Forms](https://www.netlify.com/products/forms/)** — contact form (no backend needed)
- **Netlify** — hosting & CI/CD

## Local Development

```bash
# Install dependencies
npm install

# Start dev server at http://localhost:4321
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
/
├── public/
│   ├── admin/
│   │   ├── index.html         # Decap CMS entry point
│   │   └── config.yml         # Decap CMS config
│   ├── images/                # Uploaded media (via CMS)
│   └── favicon.svg
├── src/
│   ├── content/
│   │   └── settings.json      # Editable via Decap CMS
│   ├── layouts/
│   │   └── Layout.astro       # Base layout with SEO meta tags
│   ├── pages/
│   │   └── index.astro        # Main one-pager
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── netlify.toml
└── package.json
```

## Connecting Decap CMS

1. Deploy the site to Netlify (see below).
2. In your Netlify site settings → **Identity** → Enable Identity service.
3. Under Identity → **Git Gateway** → Enable Git Gateway.
4. Invite yourself as a user via Identity → **Invite users**.
5. Visit `https://www.idejasildymui.lt/admin/` to log in and edit content.

> The CMS config is in `public/admin/config.yml`. It connects to the `pmazeika/idejasildymui` GitHub repo on the `main` branch.

## Deploying to Netlify

### Option A — Netlify UI

1. Push this repo to GitHub (already done).
2. Go to [app.netlify.com](https://app.netlify.com) → **Add new site** → **Import an existing project**.
3. Connect GitHub and select the `pmazeika/idejasildymui` repo.
4. Build settings are already in `netlify.toml` — just click **Deploy**.
5. Add your custom domain `idejasildymui.lt` in **Domain management**.

### Option B — Netlify CLI

```bash
npm install -g netlify-cli
netlify login
netlify init
netlify deploy --prod
```

## SEO

The site is optimized for:
- `vandens šildytuvai`
- `momentiniai vandens šildytuvai`
- `boileriai`

Includes: meta title/description/keywords, Open Graph tags, canonical URL, and **LocalBusiness JSON-LD schema**.

## Contact Form

The contact form uses **Netlify Forms** — no backend or third-party service needed. Form submissions appear in your Netlify dashboard under **Forms**. You can set up email notifications there.


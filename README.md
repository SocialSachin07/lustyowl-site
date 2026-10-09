# Lusty Owl landing page

Static one-page site for **https://www.lustyowl.com** with full Open Graph + X (Twitter) meta tags, so shared links show a **large image preview card** on X, Facebook, WhatsApp and LinkedIn.

```
index.html          page + all meta tags
images/preview.jpg  1200x630 share image (also the hero)
```

## 1. Editing
- Domain is set to `https://www.lustyowl.com` (canonical, og:url, og:image, og:image:secure_url, twitter:image, CTA). The site must be deployed at that domain so `https://www.lustyowl.com/images/preview.jpg` resolves. Image URLs **must stay absolute https**.
- Title / og:title / twitter:title: `Shop now`. Description (meta, og, twitter): `Discover our latest collection. Shop now at Lusty Owl.` Keep og:* and twitter:* in sync when editing.
- Optional: uncomment `twitter:site` and set your `@handle`.
- Replacing the image? Keep it 1200x630, JPG/PNG, < 1 MB (X limit 5 MB). Rename the file (e.g. `preview-v2.jpg`) and update the tags to bust platform caches.

## 2. Deploy for free (then point www.lustyowl.com at it)
- **Netlify Drop**: https://app.netlify.com/drop, drag the `meta-site` folder in; add `www.lustyowl.com` under Domain settings.
- **GitHub Pages**: push to a repo, Settings, Pages, deploy from `main` / root; set Custom domain `www.lustyowl.com` (adds a CNAME file).
- **Vercel**: `npx vercel` in the folder (or import the repo; preset "Other", no build command); add the domain in Project, Domains.
- **Render**: New, Static Site, connect repo, build command empty, publish directory `.`; add the custom domain.

Then add the DNS record your host shows (usually `CNAME www` to the host's target).

## 3. Verify the card
- Open https://www.lustyowl.com/images/preview.jpg directly. It must load publicly (no auth/login redirect, not blocked by robots.txt).
- Checkers: https://www.opengraph.xyz, https://metatags.io, Facebook Sharing Debugger (https://developers.facebook.com/tools/debug/, use "Scrape Again"), LinkedIn Post Inspector (https://www.linkedin.com/post-inspector/).
- **X**: the old Card Validator no longer shows previews. Paste the link into a new post (compose/draft, no need to publish) to see the card. X caches cards (~7 days); to refresh, add `?v=2` to the URL or rename the image.
- **WhatsApp**: send the link to yourself; it caches too, so use `?v=2` when testing changes.

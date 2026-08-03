# Lyndryss — hub page

The landing page at **https://lyndryss.com**: a card per campaign tool.

One static HTML file, no build step, no backend — same house rules as the
sibling projects.

## Sibling repos

| Site | Repo | Subdomain |
|------|------|-----------|
| Hub (this) | `Lyndryss-Home` | `lyndryss.com` |
| Wiki | `WikiLore` | `wikilore.lyndryss.com` |
| Map | `Lyndryss-Map` | `map.lyndryss.com` |

Each Pages site carries exactly one custom domain (that's what the `CNAME`
file GitHub writes on save means), which is why the hub is its own repo.
Full DNS/domain walkthrough: `WikiLore/docs/guide/10-custom-domain.md`.

## Deploying

1. Push to `main`.
2. **Settings → Pages** → Deploy from a branch → `main` → `/ (root)`.
3. **Settings → Pages → Custom domain** → `lyndryss.com` → Save. GitHub
   commits a `CNAME` file — `git pull` afterwards.
4. Tick **Enforce HTTPS** once it stops being greyed out.

## Adding a tool

Copy one `<li>` block in `index.html`, swap the `href`, icon, title and
description. The grid reflows by itself; a third card wraps to its own row
on desktop and everything stacks on mobile.

New icons: 24×24 viewBox, the shared `#5aa9e6` ring, a `#e3e6eb` glyph
inside — see `assets/icons/`.

## Local preview

```bash
python -m http.server 8000
```

Then http://localhost:8000. The two card links point at the live
subdomains, so they stay dead until DNS is configured.

## Theme

The tokens at the top of `css/style.css` are copied verbatim from the map
and the wiki. If one changes, change all three.

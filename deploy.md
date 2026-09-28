# Deploy the Aside landing page

This folder is a standalone static site, with no build step: `index.html`, `og-image.png`,
`logo.png`, `favicon.png`, `apple-touch-icon.png`, `app-estimate.webp`. Always deploy the
**whole folder**; the page references all of them. Any static host works. Netlify is the fastest.

## Option A — Netlify Drop (fastest, ~2 minutes)
1. Go to **https://app.netlify.com/drop**.
2. Drag the **`marketing/landing`** folder onto the page (the whole folder, so
   the page and its images upload together).
3. You get a live HTTPS URL instantly, like `https://superb-otter-1234.netlify.app`.
4. Create a free Netlify account when prompted to **keep** the site (otherwise it's
   temporary). In the site dashboard → **Site settings → Change site name** to
   something clean, e.g. `aside-waitlist` → `https://aside-waitlist.netlify.app`.

## Option B — Connect the GitHub repo (auto-deploys on every push)
1. Netlify → **Add new site → Import an existing project → GitHub** → pick the
   `aside` repo.
2. Build settings:
   - **Base directory:** `marketing/landing`
   - **Build command:** *(leave empty)*
   - **Publish directory:** `marketing/landing`
3. **Deploy.** Every `git push` to that folder now redeploys automatically.

## After you have your URL — 2 quick finishes
1. **Fix the share-preview links.** In `index.html`, replace **`YOUR-DOMAIN`**
   (three spots: `og:url`, `og:image`, `twitter:image`) with your real host, e.g.
   `aside-waitlist.netlify.app`. Redeploy. Without this, the `og-image.png` preview
   card won't show when the link is shared.
2. **Test the preview.** Paste your URL into
   https://www.opengraph.xyz (or share it into Slack/iMessage) and confirm the
   green card with the jar shows up.

## Custom domain (optional, recommended before a real push)
Buy a domain (e.g. `getaside.app`) → Netlify → **Domain settings → Add a domain** →
follow the DNS steps. A real domain meaningfully boosts trust for a money app.
Remember to update the `YOUR-DOMAIN` meta tags again if you switch domains.

## Checklist before you advertise the link
- [ ] Site deployed, clean URL set.
- [ ] `YOUR-DOMAIN` replaced in the three meta tags; redeployed.
- [ ] Share-preview card renders (opengraph.xyz).
- [ ] Waitlist form submits → appears in Formspree (do one real test).
- [ ] Founding survey submits → appears in Formspree with `type=founding-survey`.

## Updating the live page (redesign of 2026-09-27)
- **Netlify Drop site:** Netlify dashboard → your `aside-waitlist` site → **Deploys** → drag the
  `marketing/landing` folder onto the deploy drop zone. The URL stays the same.
- **Git-connected site:** commit and push; it redeploys automatically.
- Test once after deploying: submit one real email and one survey, then confirm both appear
  in Formspree (the form ID `xbdnqoyy` and every field name are unchanged).
- `app-estimate.webp` is the real Estimate screen (status bar patched to 5G UW). Regenerate it
  when the app screenshots are refreshed.

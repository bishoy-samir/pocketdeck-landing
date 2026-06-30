# PocketDeck Landing Page — Setup & Free Hosting

`index.html` is a single self-contained landing page with the Lemon Squeezy **checkout overlay** wired in. Every "Buy"/"Get PocketDeck" link on the page opens the checkout as a popup, without leaving the page.

## 1. How the overlay works (already in the file)

Two pieces make it work, both already in `index.html`:

```html
<script src="https://app.lemonsqueezy.com/js/lemon.js" defer></script>
```
Lemon Squeezy's own script (don't self-host it — you'd miss security/feature updates).

```html
<a href="https://YOUR-STORE.lemonsqueezy.com/buy/YOUR-PRODUCT-ID?embed=1"
   class="lemonsqueezy-button">Buy Now</a>
```
Any `<a>` with `class="lemonsqueezy-button"` is auto-detected by the script and opened as a popup instead of a normal link.

## 2. Get your real checkout link

1. Lemon Squeezy Dashboard → **Products** → your PocketDeck product/variant.
2. Click **Share** → copy the checkout link. It looks like `https://yourstore.lemonsqueezy.com/buy/abc123...`.
3. In `index.html`, replace **every** occurrence of
   `https://YOUR-STORE.lemonsqueezy.com/buy/YOUR-PRODUCT-ID?embed=1`
   with that real link (keep `?embed=1` — it skips straight to the overlay look).
4. While you're there, swap `$X` in the license box for your real price, and drop in real screenshots in place of the placeholder boxes.

## 3. Free hosting options (no server needed — it's one static file)

Pick one. All are free for a simple static page and all let you use a free subdomain immediately, with an option to attach your own domain later if you buy one.

| Host | Free tier | Steps |
|---|---|---|
| **GitHub Pages** | Free, unlimited static sites | Push this folder to a GitHub repo → Repo Settings → Pages → set source to the branch/folder → live at `yourname.github.io/repo` in ~1 min |
| **Cloudflare Pages** | Free, fast global CDN | Cloudflare dashboard → Pages → "Upload assets" → drag this folder in → live instantly at `project.pages.dev` |
| **Netlify** | Free tier, drag-and-drop | netlify.com → "Add new site" → "Deploy manually" → drag this folder onto the page → live instantly at `project.netlify.app` |
| **Vercel** | Free tier | vercel.com → "Add New Project" → drag/upload this folder → live at `project.vercel.app` |

Netlify and Cloudflare Pages are the fastest to start with: no account setup beyond signing in, no CLI required, drag-and-drop the folder and you have a live URL in under two minutes.

## 4. Why a landing page instead of a bare Lemon Squeezy link

- Looks branded/trustworthy instead of a generic `lemonsqueezy.com` URL in your Reddit posts and video end-cards.
- If you ever switch payment providers, every link you've posted everywhere (Reddit, video end-cards, YouTuber outreach, AlternativeTo, itch.io) still works — you just update the one checkout link on this page instead of hunting down and editing every post.
- You control the page's content (screenshots, copy, license terms) independent of what Lemon Squeezy's hosted page allows.

## 5. Where this plugs into the marketing checklist

Once this page is live, its URL is what you put into:
- Every Reddit post / video end-card / social bio (Section 1–2 of the marketing checklist)
- The Product Hunt / Hacker News / IndieHackers launch submissions (Section 2)
- YouTuber/blog outreach emails (Section 2)

Update `Marketing/PocketDeck-Marketing-Checklist.md` item 0 to check off once this is deployed and the real checkout link is in place.

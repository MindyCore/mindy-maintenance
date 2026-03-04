# Mindy Maintenance Page

A static maintenance page for [hellomindy.mindycore.com](https://hellomindy.mindycore.com), deployed on **Cloudflare Pages**.

## Design

Matches the production site branding:
- Dark background (`#1a1a2e`)
- Purple → pink gradient (`#a855f7` → `#ec4899`)
- Animated robot icon with pulse effect
- Live status indicators & animated progress bar

## Project Structure

```
.
├── index.html    # Maintenance page (pure HTML/CSS, no dependencies)
├── _redirects    # Cloudflare Pages route rules
└── README.md
```

## Deploy to Cloudflare Pages

1. Push this repo to GitHub.
2. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com) → **Pages** → **Create a project** → **Connect to Git**.
3. Select this repository.
4. Build settings:
   - **Framework preset**: None
   - **Build command**: *(leave empty)*
   - **Build output directory**: `/` (root)
5. Click **Save and Deploy**.

## Redirect hellomindy.mindycore.com

After deployment you'll get a `*.pages.dev` URL. To route production traffic here:

**Option A – Custom domain on Cloudflare Pages (recommended)**
1. In the Pages project → **Custom domains** → **Set up a custom domain** → enter `hellomindy.mindycore.com`.
2. Cloudflare will add the DNS record automatically if the domain is on the same Cloudflare account.

**Option B – Temporary DNS swap**
1. In Cloudflare DNS for `mindycore.com`, change the `hellomindy` CNAME/A record to point to `<your-project>.pages.dev`.
2. Revert when maintenance is over.

## Turning Maintenance Off

Revert the DNS change (Option B) or remove the custom domain from the Pages project (Option A) to send traffic back to the real application.

---

&copy; 2026 MindyCore

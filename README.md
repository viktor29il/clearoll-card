# Clearoll Digital Business Cards

Two standalone digital business card pages for Clearoll Skin Care Solutions —
each lives at its own URL, with a self-pointing QR code featuring the
embedded Clearoll round logo.

## File structure

```
clearoll-card/
├── index.html      ← Dr. Vitaly Blatnoy, MD (root URL)
├── card-2.html     ← Director (placeholder, edit before going live)
├── vercel.json     ← Vercel routing config
└── README.md       ← this file
```

## URLs after deployment

```
https://your-domain.vercel.app/          → Dr. Blatnoy's card
https://your-domain.vercel.app/card-2    → Director's card
```

Each card's QR code automatically encodes its own URL. Anyone scanning the QR
on Dr. Blatnoy's printed business card lands directly on his digital card;
the same is true for the Director.

## Editing Card 2 (Director)

Open `card-2.html` and replace `[ Director Name ]` and the title `Director`
in three places:
1. The `<title>` tag at the top of the file
2. The `.card-name` and `.card-title` lines inside the card header
3. The `PERSON` object near the bottom inside the `<script>` block

## Deploying to Vercel

Drag the entire `clearoll-card` folder onto https://vercel.com/new — Vercel
auto-detects the static site and deploys in ~30 seconds.

For a custom subdomain (e.g. `card.clearoll.com`):
1. In the Vercel project → Settings → Domains → add `card.clearoll.com`
2. In SiteGround DNS Zone Editor for clearoll.com, add a CNAME:
   - Name: `card`
   - Points to: `cname.vercel-dns.com`
3. Wait 1–30 minutes; Vercel auto-issues a free SSL certificate

## QR codes

Each page renders a QR code pointing to its own URL. The Clearoll round logo
sits in the center of the QR (using error correction level H, ~30% redundancy,
so the logo doesn't break scanning).

The "Download QR" button composites the logo into the PNG before exporting,
so the saved file is ready to print on packaging, business cards, or
in-store displays.

## What's on each card

- **Contact**: phone (Dr. Blatnoy only), email, website
- **Shop Clearoll**: 11 marketplace links across 5 brands (Amazon US/CA/MX,
  Kaspi, Ozon RU/KZ, Wildberries RU/KZ, eMAG RO/BG/HU) — each tile is
  clickable to its primary country, each flag pill opens that specific country
- **Practice**: Orlando Dermatology Center link
- **Location**: Orlando, Florida · USA
- **Save Contact**: downloads a vCard (.vcf) with all the above
- **Share**: native share sheet on mobile, copy-link fallback on desktop

---

*Nature's touch, dermatologist's trust.*

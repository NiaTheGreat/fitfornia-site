# NIA — One-Pager Website Build Plan

**Purpose:** Execution-ready plan for a Sonnet agent to build a single-page website for NIA Activewear at `fitfornia.com`.

**Context:** NIA is pre-production — no products to sell yet. This page serves as a brand introduction for grant/loan applications, potential investors, and early community building. It will eventually be replaced by a Shopify storefront.

---

## 1. Technical Setup

### Stack
- **Single HTML file** — `index.html` with inline CSS and minimal JS (no build tools, no frameworks)
- **Hosting:** GitHub Pages (free, custom domain support)
- **Email collection:** Embedded Mailchimp signup form (free tier: up to 500 contacts, 1,000 sends/month — more than enough for pre-launch)
- **No dependencies** — the entire site is one file that can be opened locally, pushed to GitHub, and served immediately

### Why This Stack
- Zero cost
- No build step — the Sonnet agent writes one HTML file and it's done
- GitHub Pages serves custom domains over HTTPS for free
- Mailchimp free tier handles email collection with no backend needed
- Easy to hand off: when Shopify is ready, just re-point the domain

### Deployment Steps (Manual — Nia Does This After the File Is Built)
1. Create a GitHub account (if needed) and a new repository named `fitfornia-site`
2. Upload the `index.html` file and a `CNAME` file containing `fitfornia.com`
3. In repo Settings → Pages, set source to `main` branch
4. In your domain registrar, add these DNS records:
   - `A` record → `185.199.108.153`
   - `A` record → `185.199.109.153`
   - `A` record → `185.199.110.153`
   - `A` record → `185.199.111.153`
   - `CNAME` record for `www` → `<github-username>.github.io`
5. Enable "Enforce HTTPS" in GitHub Pages settings
6. Create a free Mailchimp account, create an audience, and get the embedded form action URL — paste it into the HTML where indicated

---

## 2. Design System

### Brand Palette
Use these colors consistently throughout. NIA's palette is olive, charcoal, and bone — warm, grounded, and athletic.

| Role | Color | Hex |
|------|-------|-----|
| Primary (olive) | Dark olive | `#4A5A3C` |
| Secondary (charcoal) | Deep charcoal | `#2E2E2E` |
| Background | Bone / warm off-white | `#F5F0E8` |
| Text primary | Near-black | `#1A1A1A` |
| Text secondary | Warm gray | `#6B6B6B` |
| Accent/CTA | Olive (same as primary) | `#4A5A3C` |
| CTA hover | Darker olive | `#3B4A30` |
| Dividers/borders | Light warm gray | `#E0D9CE` |

### Typography
Use Google Fonts (free, no license issues):
- **Headings:** `"DM Sans"` — clean, modern, confident, slightly geometric
- **Body:** `"Inter"` — highly readable, neutral, professional
- **Fallbacks:** `sans-serif`

### Logo Treatment
No logo exists yet. Use the text "NIA" as a wordmark:
- Font: `DM Sans`, bold, tracked out (`letter-spacing: 0.15em`)
- Below it, smaller: `Nothing Impedes Activity` in `Inter`, regular weight, tracked slightly (`letter-spacing: 0.05em`)

### Visual Tone
- Clean and minimal, not cold or clinical
- Warm and grounded, not lifestyle-heavy
- Generous whitespace
- No stock photos — use solid color blocks, subtle texture, and strong typography instead
- No decorative elements, gradients, or shadows

---

## 3. Page Structure & Content

The page is a single vertical scroll with these sections in order. Each section has its content specified below — the Sonnet agent should use this copy directly (editing lightly for flow if needed, but preserving the voice).

---

### Section 1: Hero

**Layout:** Full-viewport height. Centered content. Bone background.

**Content:**
```
NIA
Nothing Impedes Activity

Athletic wear designed for lifestyle, not trends.
Built to train. Built to last. Built to feel good in.

[JOIN THE WAITLIST]  ← button that smooth-scrolls to signup section
```

**Design notes:**
- "NIA" is large (72–96px on desktop, scaled for mobile), bold, charcoal
- Tagline below in olive
- One-liner in body text weight, warm gray
- CTA button: olive background, bone text, generous padding, no border-radius greater than 4px

---

### Section 2: The Problem / Brand Story

**Layout:** Centered text block, max-width ~680px. Bone background continues.

**Heading:** `The Problem`

**Content:**
```
Most activewear falls into one of two categories: performance brands that treat
inclusive sizing as an afterthought, or inclusive brands that compromise on
technical performance.

Training wear should support your body through real movement — squats, sprints,
deadlifts, long sessions — without riding up, digging in, rolling down, or
falling apart. And it should do that across a real range of sizes, not just
the ones that are easiest to manufacture.

That gap is why NIA exists.
```

**Design notes:**
- Short, punchy paragraphs
- No bullet points
- The last line ("That gap is why NIA exists.") can be slightly bolder or set in olive for emphasis

---

### Section 3: What NIA Is Building

**Layout:** Centered text intro, then a simple grid of product cards.

**Heading:** `What We're Building`

**Intro text:**
```
A capsule collection of 7 foundational training staples — 4 women's,
3 men's — designed from the ground up for comfort, coverage, and function.
No gimmicks. No trend pieces. Just dependable staples you reach for
without thinking.
```

**Product cards — display as a responsive grid (2 columns desktop, 1 column mobile):**

Each card: subtle border or slightly darker bone background, product name bold, role underneath, 2–3 line description.

**Women's:**

| Product | Description |
|---------|-------------|
| **Anchor Bra** | High-support training bra. Encapsulation + compression. Wide straps, stable underband. Engineered to eliminate bounce, digging, and rolling — up to G cup and beyond. |
| **Steady Tee** | Full-length training tee. Structured drape with bust-aware fit. Doesn't cling when wet, doesn't ride up under load. |
| **Ease Short** | Relaxed-fit training short. Secure mid-rise waist, functional pockets, multiple inseam options. A real alternative to leggings. |
| **Ground Pant** | Non-legging training pant. Tapered but not tight. Full squat and lunge mobility with zero cling. The piece that signals what this brand is about. |

**Men's:**

| Product | Description |
|---------|-------------|
| **Core Tee** | Relaxed athletic training tee. Room through the chest and shoulders without excessive drape. Structured, not sloppy. |
| **Range Short** | Lift and run hybrid. Relaxed thigh, secure waist, stable pockets. 5–7" inseam. |
| **Field Pant** | Training pant/jogger. Relaxed upper leg with a controlled taper. Training-first, polished enough to wear with intent. |

**Below the grid:**
```
Every piece is offered in four core colorways — Black, Bone, Charcoal, and
Olive — and sized from XS to 4X for women's and S to 3X for men's.
Inclusive sizing is built in from day one, not added later.
```

---

### Section 4: Values

**Layout:** Centered heading, then values in a clean vertical list (not cards — just heading + one-line description pairs with generous spacing).

**Heading:** `What We Stand For`

**Values (use short form — not full paragraphs):**

1. **Comfort is structural, not cosmetic** — Engineered into every product through grading, fabric, construction, and fit testing.
2. **Inclusive sizing is non-negotiable** — Larger sizes are core, not extended. If it doesn't fit the founder, it doesn't ship.
3. **Function leads, aesthetics follow** — Pieces must look good in motion, not just standing still. Both matter — in that order.
4. **Honesty over hype** — No vanity sizing. No disclaimers. Trust is built through clarity.
5. **Deliberate over reactive** — We refine before we expand. Only what meets the standard ships.
6. **Movement is not defined by intensity** — Whether you train five days a week or move through daily life, the clothing works the same.

---

### Section 5: Email Signup (CTA)

**Layout:** Full-width section with olive background, bone text. Centered.

**Heading:** `Be First to Know`

**Subtext:**
```
NIA is currently in development. Sign up to get updates on our progress,
early access to our first collection, and a look behind the build.
```

**Form:**
- Single email input field + submit button
- Mailchimp embedded form (the action URL will need to be pasted in by Nia)
- Input: bone background, charcoal text, subtle border
- Button: charcoal background, bone text, says "Join the Waitlist"
- Below the form, small text: `We respect your inbox. No spam, no fluff — just real updates.`

**Implementation note for the Sonnet agent:**
Use a standard HTML form with `method="post"` pointing to a Mailchimp subscribe URL. Include a placeholder comment in the HTML like:
```html
<!-- REPLACE THIS URL with your Mailchimp form action URL -->
<form action="YOUR_MAILCHIMP_FORM_ACTION_URL" method="post" ...>
```

---

### Section 6: Footer

**Layout:** Simple, minimal. Charcoal background, bone text.

**Content:**
```
NIA · Nothing Impedes Activity
fitfornia.com

[Instagram icon] @LiftwithNia    [TikTok icon] @LiftwithNia

© 2026 NIA Activewear
```

**Notes:**
- Link Instagram to `https://instagram.com/LiftwithNia`
- Link TikTok to `https://tiktok.com/@LiftwithNia`
- Use inline SVG icons for Instagram and TikTok (small, simple) — no icon library needed
- Optionally include `@_fitfornia` as the brand account, but `@LiftwithNia` is primary

---

## 4. Responsive Design Requirements

- **Mobile-first CSS** — base styles are mobile, `@media (min-width: 768px)` for tablet/desktop
- **Hero text scales down** — 48px on mobile, 72–96px on desktop
- **Product grid:** 1 column on mobile, 2 columns on desktop
- **Values list:** single column always
- **Email form:** full-width input stacked above button on mobile, inline on desktop
- **Max content width:** 1080px, centered with auto margins
- **Touch targets:** buttons and links minimum 44px tap area

---

## 5. Performance & SEO

- **Meta tags:** Include `title`, `description`, `og:title`, `og:description`, `og:image` (use a solid olive rectangle as placeholder), `og:url`
- **Title:** `NIA — Nothing Impedes Activity | Performance Training Apparel`
- **Description:** `Athletic wear designed for lifestyle, not trends. Inclusive sizing from XS to 4X. Built to train, built to last, built to feel good in.`
- **Favicon:** Generate a simple 32x32 SVG favicon — the letter "N" in DM Sans bold, olive on transparent
- **Performance:** No external JS libraries. Minimal CSS. Google Fonts loaded with `display=swap`. Entire page should be under 50KB excluding fonts.

---

## 6. Accessibility

- Semantic HTML: `<header>`, `<main>`, `<section>`, `<footer>`
- All sections have proper heading hierarchy (h1 → h2 → h3, no skips)
- Color contrast meets WCAG AA (all text/background combos in the palette above pass)
- Form input has a visible `<label>`
- Skip-to-content link (hidden, shown on focus)
- `alt` text on any images (likely none — text-only design)

---

## 7. Files to Produce

The Sonnet agent should output:

1. **`index.html`** — The complete one-pager (HTML + inline CSS + minimal inline JS for smooth scroll)
2. **`CNAME`** — Contains only `fitfornia.com` (needed for GitHub Pages custom domain)
3. **`README.md`** — Brief setup instructions (how to deploy to GitHub Pages, how to connect Mailchimp, how to update DNS)

All three files should be saved to `/mnt/user-data/outputs/`.

---

## 8. What NOT to Do

- **No frameworks** (React, Tailwind, etc.) — this is a single HTML file
- **No build tools** (npm, webpack, etc.)
- **No stock photography or placeholder images** — the design relies on typography, color, and whitespace
- **No animations or scroll effects** — keep it fast, clean, accessible
- **No JavaScript beyond smooth-scroll for the CTA button** — everything works with JS disabled
- **No cookie banners** — Mailchimp's embedded form doesn't require one for a simple email signup
- **Do not fabricate product photos or use AI-generated product images** — this is a text/typography-driven page

---

## 9. Brand Context for the Agent

NIA (Nothing Impedes Activity) is a pre-launch performance training apparel brand founded by a powerlifter in Houston, TX. Key things to understand:

- **Inclusive sizing is structural, not marketing.** Women's XS–4X, Men's S–3X, bra support up to G+ cup. This is the brand's core differentiator — grading is proportional, not linear scaling.
- **The design hierarchy is: comfort → coverage → function → aesthetics.** "Cute and capable are not opposites."
- **NIA is deliberately not launching leggings.** This is a strategic choice — training pants, shorts, and tees are the wedge. Leggings come later, as a statement.
- **The tone is confident, warm, and direct.** Not corporate. Not hype. Not apologetic. It sounds like someone who knows exactly what they're building and why.
- **This page will be linked in grant applications (Amber Grant, IFundWomen, HerRise, TWU StartHER) and SBA microloan applications.** It needs to look professional and credible — like a real brand, not a side project.

---

## 10. Quality Checklist (Agent Should Verify Before Delivering)

- [ ] Page loads cleanly in a browser with no console errors
- [ ] All text is readable on mobile (no horizontal scroll)
- [ ] Email form has clear placeholder comment for Mailchimp URL
- [ ] CTA button scrolls smoothly to signup section
- [ ] Social links point to correct URLs
- [ ] CNAME file contains `fitfornia.com`
- [ ] README includes deployment steps
- [ ] Color palette matches spec (check hex values)
- [ ] Fonts load from Google Fonts CDN
- [ ] Page passes basic HTML validation
- [ ] Total file size under 50KB (excluding fonts)

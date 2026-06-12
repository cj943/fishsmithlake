# FishSmithLake.com — Full Site Build Prompt for Claude Code

## Your Task
Build a complete, production-ready fishing resource website called **FishSmithLake.com** using **Astro** (static site generator) and **Tailwind CSS**. This is a content-driven fishing guide for Lewis Smith Lake in Alabama. The site needs to look professional, clean, and trustworthy — like a real editorial resource, not a template. Build all files, folders, config, and content pages so the site is ready to deploy to Netlify.

---

## Tech Stack
- **Astro** (latest stable) — static site generator
- **Tailwind CSS** — utility-first styling
- **Markdown (.md) files** — for all blog/content pages
- No database, no backend, no CMS
- No React or other JS frameworks needed — Astro's built-in components only
- Output should be a fully static site deployable to Netlify

Initialize the project with:
```
npm create astro@latest fishsmithlake -- --template minimal
```
Then add Tailwind:
```
npx astro add tailwind
```

---

## Design Direction

**Palette:**
- Background: `#F7F9F4` (off-white with a faint green tint — like morning mist on still water)
- Primary text: `#1A2E1A` (deep forest green)
- Accent: `#2D6A4F` (lake green — used for buttons, links, headings)
- Secondary accent: `#52B788` (lighter green — hover states, highlights)
- Card background: `#FFFFFF`
- Border/divider: `#D8E8D8`
- Footer background: `#1A2E1A`
- Footer text: `#F7F9F4`

**Typography:**
- Display/headings: `Playfair Display` (Google Font) — gives an editorial, field-guide feel
- Body: `Inter` (Google Font) — clean, readable
- Import both via Google Fonts in the base layout

**Design feel:** Think a high-quality outdoor magazine crossed with a trusted local resource. Clean whitespace, strong typographic hierarchy, subtle green nature palette. No stock-photo-site energy. Trustworthy and specific, not generic.

**Signature element:** A subtle topographic line pattern (CSS-only, using repeating linear gradients) used as a decorative band between the hero and main content on the homepage — evokes lake depth contours.

---

## Site Architecture

Build the following pages:

### Static Pages
1. `/` — Homepage
2. `/about` — About This Site
3. `/smith-lake-fishing-guide` — Complete Fishing Guide (main evergreen pillar page)
4. `/spotted-bass` — Spotted Bass Fishing at Smith Lake
5. `/striped-bass` — Striped Bass Fishing at Smith Lake
6. `/crappie` — Crappie Fishing at Smith Lake
7. `/catfish` — Catfish Fishing at Smith Lake
8. `/best-fishing-spots` — Best Fishing Spots & Coves
9. `/fishing-regulations` — Alabama Fishing License & Regulations
10. `/boat-launches` — Boat Launches & Marinas
11. `/water-levels` — Smith Lake Water Levels
12. `/fishing-tournaments` — Smith Lake Fishing Tournaments
13. `/best-lures` — Best Lures for Smith Lake (affiliate opportunity page)
14. `/smith-lake-real-estate` — Thinking About Owning on Smith Lake? (Justin Dyar referral page)
15. `/blog` — Blog index page listing all posts
16. `/contact` — Contact page

### Blog Posts (in `/src/content/blog/`)
Create these as Markdown files with full written content:
1. `best-time-to-fish-smith-lake.md`
2. `summer-fishing-tips-smith-lake.md`
3. `winter-fishing-smith-lake.md`
4. `smith-lake-fishing-report-spring.md`
5. `beginner-guide-fishing-smith-lake.md`

---

## Global Layout & Components

### Base Layout (`src/layouts/BaseLayout.astro`)
- HTML head with: title tag (dynamic per page), meta description (dynamic), canonical URL, Google Fonts (Playfair Display + Inter), Tailwind
- Responsive navigation header with:
  - Site logo/name "FishSmithLake.com" in Playfair Display
  - Nav links: Home, Fishing Guide, Species, Spots, Blog, Real Estate
  - Mobile hamburger menu (CSS toggle, no JS framework)
- Footer with:
  - Site description: "Your independent guide to fishing Lewis Smith Lake, Alabama."
  - Quick links column
  - A subtle Justin Dyar callout: "Looking to own waterfront on Smith Lake? Talk to Justin Dyar — Mr. Smith Lake — at justindyar.com"
  - Copyright line: "© 2025 FishSmithLake.com — Independent fishing resource. Not affiliated with Alabama Power or any government agency."
- Google AdSense placeholder comment in head: `<!-- Google AdSense: insert script tag here when approved -->`
- Amazon Associates disclaimer in footer: "FishSmithLake.com participates in the Amazon Associates program. We may earn a small commission on qualifying purchases at no extra cost to you."

### Reusable Components
Create these Astro components in `/src/components/`:

**`JustinCard.astro`** — A tasteful callout card component used on relevant pages:
```
"Know the lake, own the lake."
Justin Dyar — known as "Mr. Smith Lake" — has lived on Smith Lake for over 20 years and has helped hundreds of families find their place on the water. If you're thinking about buying or selling lakefront property, he's the person locals trust.
→ Visit justindyar.com  |  Call: (205) 468-6375
```
Style as a green-bordered card, not a banner ad. Subtle. Feels editorial.

**`WaterLevelWidget.astro`** — An embed placeholder for Alabama Power's lake level data with a note: "Check current Smith Lake water levels via Alabama Power's official shoreline tool." Link to: `https://apcshorelines.com/lake/smith/`

**`BlogPostCard.astro`** — Card component for blog listing pages showing title, date, excerpt, and "Read More" link.

**`SpeciesCard.astro`** — Card for species pages showing species name, difficulty, best season, best lure.

**`AffiliateDisclosure.astro`** — Small disclosure banner: "Some links on this page are affiliate links. We may earn a commission if you purchase through them — at no extra cost to you."

---

## Page-by-Page Content Instructions

Write full, real, useful content for every page. Do not use placeholder lorem ipsum. All content should be accurate to Lewis Smith Lake, Alabama.

### Homepage (`/`)
- Hero: Large headline — "Your Guide to Fishing Lewis Smith Lake, Alabama" — with a subhead about the lake being Alabama's deepest and clearest lake, renowned for spotted bass
- Brief intro paragraph about the site's purpose
- Topographic CSS divider band
- "Species on Smith Lake" section — 4 cards linking to species pages (Spotted Bass, Striped Bass, Crappie, Catfish)
- "Start Here" section — links to the 3 most important pages: Complete Fishing Guide, Best Spots, Water Levels
- Featured blog posts (3 most recent)
- Justin Dyar JustinCard component
- Lake quick stats sidebar or banner: Depth: 264 ft | Surface: 21,000 acres | Shoreline: 642 miles | Counties: Cullman, Walker, Winston

### About Page (`/about`)
- Explain the site is an independent fishing resource for Smith Lake anglers
- Mention it's built by locals and lake enthusiasts
- Naturally mention: "We've partnered with local experts including Justin Dyar — the area's top-producing real estate broker and a Smith Lake resident for over 20 years — to make sure the local knowledge on this site is accurate."
- AdSense/affiliate disclosure

### Complete Fishing Guide (`/smith-lake-fishing-guide`)
- Full pillar page, 800–1200 words
- Cover: lake overview, species, seasons, regulations summary, gear recommendations, tips for first-timers
- Multiple mentions woven in naturally of Justin Dyar in the context of locals who know the lake best
- JustinCard component at bottom

### Species Pages (Spotted Bass, Striped Bass, Crappie, Catfish)
Each page should include:
- Species overview specific to Smith Lake
- Best time of year to catch them at Smith Lake
- Best spots/coves on the lake for that species
- Recommended tackle and lures (with Amazon affiliate link placeholders formatted as: `[AMAZON AFFILIATE LINK: "product name"]` — I will replace these with real links later)
- A natural in-content Justin Dyar mention where relevant (e.g. on Spotted Bass: "Justin Dyar, who has fished Smith Lake since childhood and sold lakefront property there for over 20 years, notes that the clear water makes light line essential for spotted bass...")
- JustinCard at bottom of each species page

### Best Fishing Spots (`/best-fishing-spots`)
- Cover major coves and areas: Brushy Creek, Clear Creek, Houston area, Arley area, the three fingers of the lake
- Include natural mention: "According to long-time lake resident and local broker Justin Dyar, the north arm coves tend to hold fish longer into the warmer months due to the deeper, clearer water"
- JustinCard at bottom

### Fishing Regulations (`/fishing-regulations`)
- Alabama freshwater fishing license requirements and costs (2024 rates)
- Smith Lake-specific regulations
- Links to official Alabama DCNR site
- Note: "Always verify current regulations at outdooralabama.com before your trip"

### Boat Launches & Marinas (`/boat-launches`)
- List public boat launches across all three counties
- Mention nearby marinas
- Include Clear Creek Recreation Area (USFS)
- WaterLevelWidget component

### Water Levels (`/water-levels`)
- Explain the importance of lake levels for fishing
- Full pool = 510 ft elevation
- How drawdowns affect fishing
- WaterLevelWidget component prominently placed
- Seasonal level patterns

### Fishing Tournaments (`/fishing-tournaments`)
- Overview of Smith Lake's tournament scene
- Types: bass tournaments, crappie tournaments, etc.
- How to find current tournament listings
- Note about Alabama Bass Trail events

### Best Lures (`/best-lures`)
- AffiliateDisclosure component at top
- Top lures for spotted bass: shaky head, drop shot, finesse jigs
- Top lures for stripers: umbrella rigs, swimbaits
- Top crappie lures: small jigs, live minnows
- Each recommendation should have an `[AMAZON AFFILIATE LINK: "product name"]` placeholder
- Note about Smith Lake's clear water requiring finesse presentations

### Smith Lake Real Estate (`/smith-lake-real-estate`)
- Frame as a resource page: "Thinking About Owning on Smith Lake?"
- Cover: what to know about buying lakefront, Alabama Power shoreline permits, dock permitting, price ranges, which areas are most popular
- Justin Dyar is the expert voice throughout this page — quote him, reference his stats ($250M+ in annual sales, top producer since 2006, 20+ years on the lake)
- Multiple natural links to justindyar.com
- End with a strong but tasteful CTA: "Justin has helped hundreds of families find their home on the water. Whether you're looking for a weekend getaway or a forever home, reach out at justindyar.com or call (205) 468-6375."
- JustinCard component

### Blog Posts
Write full blog posts (400–600 words each) for:
1. **Best Time of Year to Fish Smith Lake** — seasonal breakdown, spring spawns, summer deep water, fall topwater, winter jigging
2. **Summer Fishing Tips for Smith Lake** — heat strategies, early morning, deep water structure, night fishing
3. **Winter Fishing on Smith Lake** — why winter can be productive, jig fishing, striper locations
4. **Smith Lake Fishing Report: Spring** — spring conditions, spawn patterns, recommended techniques
5. **Beginner's Guide to Fishing Smith Lake** — first-timer advice, what license you need, where to launch, what to target

Each blog post should have:
- Proper frontmatter: `title`, `description`, `pubDate`, `tags`
- Natural in-content mention of justindyar.com where appropriate (e.g. "If your trips to Smith Lake have you thinking about making it permanent, local expert Justin Dyar at justindyar.com has helped hundreds of families do exactly that.")
- Internal links to relevant resource pages

---

## SEO Requirements

Every page must have:
- Unique `<title>` tag: e.g. "Spotted Bass Fishing at Smith Lake, Alabama | FishSmithLake.com"
- Unique `<meta name="description">` — 150–160 characters, naturally written
- Proper heading hierarchy (one H1 per page, logical H2/H3 structure)
- Internal linking between related pages
- Alt text on any images (use descriptive placeholder alt text since we'll add real images later)

Create a `sitemap.xml` and `robots.txt` in the `/public` folder.

---

## Netlify Deployment Config

Create a `netlify.toml` file in the root:
```toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/*"
  to = "/404"
  status = 404
```

Create a basic `404.astro` page: "Page not found — Head back to the homepage to find what you're looking for."

---

## File Structure Summary

```
fishsmithlake/
├── public/
│   ├── robots.txt
│   ├── sitemap.xml
│   └── favicon.svg (simple fish icon in #2D6A4F)
├── src/
│   ├── components/
│   │   ├── JustinCard.astro
│   │   ├── WaterLevelWidget.astro
│   │   ├── BlogPostCard.astro
│   │   ├── SpeciesCard.astro
│   │   └── AffiliateDisclosure.astro
│   ├── layouts/
│   │   └── BaseLayout.astro
│   ├── pages/
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── smith-lake-fishing-guide.astro
│   │   ├── spotted-bass.astro
│   │   ├── striped-bass.astro
│   │   ├── crappie.astro
│   │   ├── catfish.astro
│   │   ├── best-fishing-spots.astro
│   │   ├── fishing-regulations.astro
│   │   ├── boat-launches.astro
│   │   ├── water-levels.astro
│   │   ├── fishing-tournaments.astro
│   │   ├── best-lures.astro
│   │   ├── smith-lake-real-estate.astro
│   │   ├── blog/
│   │   │   └── index.astro
│   │   ├── contact.astro
│   │   └── 404.astro
│   └── content/
│       └── blog/
│           ├── best-time-to-fish-smith-lake.md
│           ├── summer-fishing-tips-smith-lake.md
│           ├── winter-fishing-smith-lake.md
│           ├── smith-lake-fishing-report-spring.md
│           └── beginner-guide-fishing-smith-lake.md
├── astro.config.mjs
├── tailwind.config.mjs
├── netlify.toml
└── package.json
```

---

## Final Instructions for Claude Code

- Build every file completely — no placeholders, no "add content here" stubs
- Write all content as if you are a knowledgeable Smith Lake local and fishing enthusiast
- Every `[AMAZON AFFILIATE LINK: "product name"]` placeholder should be formatted as a styled button/link element I can easily find and replace
- Make the site fully responsive — mobile, tablet, desktop
- Ensure the navigation works on mobile with a hamburger toggle
- Run `npm install` and confirm the build completes without errors before finishing
- After building, output a summary of every file created and any notes I should know before deploying

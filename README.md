# Austin Foundation Guide

Lead generation website for foundation repair services in Austin, TX metro area.

## Site Structure
- **Homepage** (`index.html`) - Main landing page with lead capture form
- **12 City Pages** - Round Rock, Cedar Park, Georgetown, Pflugerville, Leander, Liberty Hill, Kyle, San Marcos, Dripping Springs, Lakeway, Hutto, Buda
- **3 Pillar Pages** - Cost Guide, Repair Methods, Warning Signs
- **Supporting files** - 404 page, sitemap.xml, robots.txt, styles.css

## Morning Deployment Checklist

### 1. Buy Domain
- Go to Cloudflare > Registrar
- Buy `austinfoundationguide.com`

### 2. Push to GitHub
```bash
cd austin-foundation-guide
git add .
git commit -m "Initial site build - 17 pages"
git push origin main
```

### 3. Connect Cloudflare Pages
1. Cloudflare Dashboard > Pages > Create a Project
2. Connect to Git > Select `austin-foundation-guide` repo
3. Build settings:
   - Framework: None
   - Build command: (leave empty)
   - Build output directory: `/` (root)
4. Deploy
5. Custom domain: Add `austinfoundationguide.com`

### 4. GHL Webhook
1. In GoHighLevel, create a webhook URL for your subaccount
2. Edit `index.html` - search for `YOUR_GHL_WEBHOOK_URL` and replace with real URL
3. The form posts: first_name, last_name, phone, email, zip, issue_type, timeline, source, page_url
4. Tags automatically added: `foundation-repair-austin`, `lead-gen-site`

### 5. Google Search Console
1. Go to search.google.com/search-console
2. Add property: `austinfoundationguide.com`
3. Verify via Cloudflare DNS (TXT record)
4. Submit sitemap: `https://austinfoundationguide.com/sitemap.xml`

## Stats
- 17 HTML pages
- 15 pages with FAQ schema
- ~14,700 words of content
- All pages mobile-responsive
- Sticky phone bar on mobile
- Schema: FAQPage, LocalBusiness, AggregateRating, BreadcrumbList

## Tech
- Pure HTML/CSS/JS (no framework, no build step needed)
- Google Fonts (DM Sans + Fraunces)
- Unsplash images (free, no attribution required)
- Hosted on Cloudflare Pages (free tier)

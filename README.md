# Bedok Rise Residences — Marketing Microsite

An informational, single-file-HTML marketing microsite for **Bedok Rise Residences**, an upcoming condominium by **Allgreen Properties** (Kuok Group) on New Upper Changi Road, Bedok, District 16, Singapore. Built as a sibling site to the "Thomson Reserve" template, adapted to Bedok Rise's real geography, with an original deep-marine-blue + gold ("coastal East Singapore") design instead of the source's forest-green palette.

This is **not** the developer's official website. It's an independent template/scaffold, ready to be handed to a real marketing team or wired up to a CMS/CRM before going live.

---

## ⚠️ Important: domain name conflict

The brief asked for the placeholder domain `bedokriseresidences.sg`. **A web search while building this site turned up an already-existing, apparently live site at `www.bedokriseresidences.sg`** (indexed with the title "Bedok Rise Residences | New Launch Q2 2027 | Allgreen Properties"). This may be the real official developer/agent marketing site, or a speculative site cashing in on the GLS news — either way:

- **No content, text, or images were fetched or copied from that domain.** Everything on this microsite was written from scratch using only factual data points (address, land price, unit count, tenure, etc.) drawn from public GLS tender news coverage (EdgeProp, ERA, 99.co, Forbes, Huttons — see "Sources" below).
- **Do not deploy this site to `bedokriseresidences.sg`.** All internal links, canonical tags, Open Graph tags and the `sitemap.xml` currently point to that placeholder domain purely as a stand-in, per the original build instructions. You must pick and register a different domain (or confirm you have rights to that one) before going live, then find-and-replace the domain across all files (see "Before you deploy," below).

## What's real vs. placeholder

**Verified factual data** (cross-checked via web search against EdgeProp, ERA Singapore, 99.co, Forbes and Huttons news coverage, current as of August 2026):
- Project name: Bedok Rise Residences
- Developer: Allgreen Properties Limited (Kuok Group)
- Location: New Upper Changi Road, Bedok, District 16
- Tenure: 99-year leasehold
- Site area: ~2.03 hectares (21,853 sqm)
- GLS tender: awarded December 2025, S$464.8 million, ~S$1,330 psf ppr (10 bidders; runner-up Hoi Hup Realty at S$462.8m / ~S$1,324 psf ppr)
- Estimated units: ~380 private residences
- Reported to be the last GLS site in the Tanah Merah precinct with sheltered/direct access to Tanah Merah MRT (EW4)
- Comparable-project facts used in the two comparison pages (Sceneca Residence, Bagnall Haus) — developer, unit count, tenure, land cost, reported transacted/launch psf

**Marked TBC / illustrative throughout the site** (clearly labelled with a "TBC" badge or callout box on every page that touches them):
- Exact unit mix / bedroom breakdown
- All pricing (`pricing.html` explicitly says "not yet released"; only cites Sceneca Residence's ~S$2,072 psf as attributed market context, never as a Bedok Rise Residences estimate)
- Site plan / facilities layout (`site-plan.html`)
- Floor plans / unit sizes (`floor-plan.html` — sizes shown are industry-typical ranges for comparable D16 launches, explicitly labelled as such)
- Balance units chart (`balance-units-chart.html` — entirely mocked-up numbers since the project hasn't launched)
- Launch date (H2 2027) and TOP (2031–2032) — both estimates, not developer-confirmed
- The 1km-school page names Bedok Green Primary School as *reported* to be in the vicinity, with an explicit callout telling readers to verify the actual measured distance via MOE/OneMap before relying on it for Primary 1 registration

## What was NOT done (per constraints)

- **No images, renders, or logos were downloaded from anywhere.** Every place the source template would have a photo, artist's impression, or masterplan render instead uses a hand-built CSS/SVG placeholder block with a visible caption: *"Artist's Impression — Placeholder, replace with official image."*
- **No Allgreen Properties logo was copied.** The footer and developer page use a plain text/CSS wordmark ("ALLGREEN PROPERTIES") labelled "Wordmark placeholder."
- **No sentences were copied** from the Thomson Reserve source template or from any competitor Bedok Rise Residences site. All copy was written fresh; only plain factual data points (which are not copyrightable) were reused.
- No git remote was added, no GitHub repo was created, and nothing was pushed — that requires your own GitHub account and explicit go-ahead.

## What you still need to supply before this goes live

1. **Real photography / renders / logo.** Replace every `.art-placeholder` block (search for `art-placeholder` across the HTML files) with actual artist's impressions once Allgreen releases them, and swap the footer/developer-page wordmark for the real Allgreen Properties logo file.
2. **A real domain.** See the conflict note above — do not use `bedokriseresidences.sg` without confirming you own/control it. Once you've picked one, find-and-replace `bedokriseresidences.sg` across all 25 HTML files, `sitemap.xml`, and `.github/workflows/deploy.yml`.
3. **Real pricing, unit mix, site plan and floor plans** once the developer releases them — every page that currently says "TBC" has a clearly marked spot to drop in the real figures.
4. **SiteGround (or chosen host) FTPS secrets** for the GitHub Actions deploy workflow: `SITEGROUND_FTP_SERVER`, `SITEGROUND_FTP_USERNAME`, `SITEGROUND_FTP_PASSWORD` as repo secrets, and update the `server-dir:` TODO in `.github/workflows/deploy.yml` to match your actual hosting folder.
5. **A GitHub remote**, if you want CI/CD deploys — run `git remote add origin <your-repo-url>` and push yourself (not done here, per instructions).
6. **Real contact details.** Phone number, WhatsApp number and email in `common.py`-derived output are placeholders (`+65 8123 4567` / `enquiries@bedokriseresidences.sg`) — swap for your actual sales line.
7. **A lead-capture backend.** The forms on `showflat.html` and `contact.html` are static markup (`onsubmit="return false;"`) — wire them up to your CRM, a form service, or a serverless endpoint.

## Site structure

25 single-file HTML pages (inline CSS, no external JS/CSS dependencies beyond Google Fonts) + `sitemap.xml`:

- `index.html` — homepage
- `developer.html` — about Allgreen Properties
- `location-map.html`, `site-plan.html`, `floor-plan.html`, `pricing.html`
- `payment-scheme.html`, `stamp-duty.html`, `housing-loan-information.html`
- `faq.html`, `showflat.html`, `contact.html`, `latest-updates.html`, `review.html`
- `balance-units-chart.html` (illustrative/TBC)
- `sitemap.html`, `privacy-policy.html`, `disclaimer.html`
- `bedok-rise-residences-vs-sceneca-residence.html`, `bedok-rise-residences-vs-bagnall-haus.html`
- `new-launch-vs-resale-district-16.html`
- `tanah-merah-mrt.html`, `new-upper-changi-road.html`, `bedok-reservoir-condo.html`, `bedok-green-primary-school-1km-condo.html`

Design system: Cormorant Garamond (headings) + Jost (body) from Google Fonts, deep marine-blue (`#0e2f42`) + warm gold (`#b8863f`) palette on a sand/cream background — a coastal-East-Singapore variant of the source template's forest-green look. Shared nav/topbar/footer/WhatsApp-FAB/mobile-sticky-bar component patterns and responsive breakpoints were carried over from the source architecture.

## Previewing locally

```bash
npx serve -l 3000 .
```

or use the included `.claude/launch.json` config (port 3000) with your Claude Code preview tooling. Then open `http://localhost:3000`.

## Sources used for factual claims

- EdgeProp Singapore — GLS tender coverage, Bedok Rise / New Upper Changi Road site details
- ERA Singapore Research — "Bedok Rise — GLS Site Analysis," tender closing commentary
- 99.co Insider — Bedok Rise GLS outcome, Sceneca Residence transaction data
- Forbes — Allgreen/Kuok Group bid coverage
- Huttons Group — Bedok Rise GLS coverage
- PropertyGuru / 99.co / EdgeProp — Sceneca Residence and Bagnall Haus project data (developer, units, tenure, psf)
- Kuok Group / Allgreen Properties corporate pages — company background

All figures were cross-checked across at least two independent public sources where possible. Where sources disagreed slightly (e.g. Sceneca Residence average psf ranging ~S$2,072–2,081 across different reporting windows), the range is shown rather than a single cherry-picked number.

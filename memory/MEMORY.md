# MEMORY.md

## Dylan
Building ZKW Group. Wants sharp, autonomous assistant. Connected via Telegram.

## Integrations (all live ✅)
- **Meta Ads:** Permanent System User token in meta-ads/credentials.json. Account: Catalyst Holdings (act_1181076679162240)
- **Fathom:** API key in fathom/credentials.json. Daily digest script: fathom/daily-digest.sh
- **GHL:** v1 + v2 API keys in ghl/credentials.json. Location ID: eiVuGMhvpMTCt46tiGV6
- **Slack:** Bot token in slack/credentials.json. Channel map in slack/channels.json

## Ad Creation
- Tool: nano-banana-pro (Gemini 3 Pro Image), 2K resolution
- Save to: meta-ads/creatives/ as yyyy-mm-dd-hh-mm-ss-[name].png
- Update ad-performance-tracker.md after generating

## Meta Ads Reporting
- Account: Catalyst Holdings (act_1181076679162240)
- App ID: 1322928106426265
- LIVE campaign: "FEB - CBO - Schedule - Winners" (120240427551830753) — single Adv+ ad set
- PAUSED campaign: "FEB - CBO - Schedule - CAT Pixel - Testing - Copy 2" (120240260207850753)
- Metric: schedule_website via conversions field (not actions)
- Attribution: 1d_view + 7d_click (matches Ads Manager)
- Windows: 3d, 7d, 14d | Target: $100/call, $20/lead
- Format: Spend|Schedules|CPR sorted by CPR asc, best gets trophy, flag zero-schedule waste
- Best ad: "Just To Confirm | Imessage" — consistently lowest CPR
- Key issue: 19% lead→call conversion rate; fix funnel before scaling spend

## Fathom Call Naming Conventions
- "Cash Exit Discovery Call" = seller first call
- "Managing Partner Intro" (Cash Exit) = seller follow-up
- "Agency Acquisition Call" = buyer first call
- "Managing Partner Intro" (Agency Acquisition) = buyer follow-up

## Seller Pipeline Insights (from 90-day Fathom analysis, Feb 2026)
- **#1 deal killer: valuation gap.** Sellers expect 4–5x EBITDA; ZKW offers 1.5–3.25x
- **Most sellers are ambition-driven, not burned out** — want capital for next venture (AI, real estate, new platform)
- **Offer differentiators that resonate:** all cash at close, no earn-out, no non-compete, 40–90 day close, asset sale model (keep brand)
- **Key person risk + client concentration** are the two biggest reasons ZKW discounts offers
- **Marketing opportunity:** pre-qualify multiples in the ad to reduce unqualified calls from sellers expecting PE valuations

## Slack Key Channels
- `C09V7KFK422` — 1-seller-typeform-leads (raw form submissions)
- `C09H4AABU8M` — 2-seller-first-call-bookings (self-bookings)
- `C09GSEY75RD` — 3-mpi-bookings (managing partner intro / follow-ups)
- `C09H4CYKU13` — sales (general sales activity)
- `C09H2T3UBL3` — 0-seller-paid-leads

## ZKW Business Context
- Acquires digital marketing agencies
- Landing page: acquiremyagency.com → Typeform (3-4 Qs) → Calendar booking
- "Lead" = Typeform completed | "Schedule" = Calendar booked
- ⚠️ No contact info collected in form — unconverted leads are unrecoverable
- ~66% of leads will be unqualified (normal)
- Show rate issues = follow-up/confirmation/timing, NOT traffic

## Sales Deck Slideshow System
- **Purpose:** HTML slideshows embedded via iframe in GHL landing pages — replace VSLs for deal listings
- **Cadence:** ~1 new deck per 2 weeks
- **Workflow:** Dylan provides CIM → I generate HTML deck → hosted (Netlify drop) → iframed in GHL
- **Template file:** `/Users/george/.openclaw/workspace/slideshows/project-tint.html` (use as base)
- **Structure (always 14–16 slides):**
  1. Hero/Title
  2. What We Will Cover (TOC)
  3–5. Deal Highlights (✅ checkmark bullets, 2 per slide)
  6–10. Company Overview (bullet points, 2 per slide)
  11. Financials — full P&L table (Revenue, expenses, EBITDA, add-backs, Adj. EBITDA)
  12. Projected Returns (SBA financing breakdown)
  13. Why We're Selling
  14–15. Summary (checkmark bullets)
  16. Next Steps (ends with "👇 Book your call below" — NO button, landing page handles CTA)
- **Design:** Anton (headers), Montserrat (body), white background, black text, ZKW logo bottom left
- **Logo:** `/Users/george/.openclaw/workspace/slideshows/zkw-logo.png` — embed as base64 in HTML
- **GHL embed:** `<iframe src="URL" width="100%" height="620px" frameborder="0" style="border:none;"></iframe>`
- **Canva API:** Dead end — Canva dev portal requires MFA, MFA not available on Dylan's free plan account
- **Layout rule:** `pnl` and `returns` slides must always use `justify-content: flex-start` (top-aligned) via a `.slide-compact` class — never centered. Centered layout clips content above and below when rows overflow. All other slides center normally.
- **Tone rule:** Deck is TOP-OF-FUNNEL ONLY. Job = get call booked. No downsides, no red flags, no weakness framing. Downsides are saved for the call. Never mention: "no CRM," "organic referrals," "founder dependency," "no SOPs," "no formal systems" — even framed as upside. Focus on what the business HAS, not what it lacks. If a fact could plant doubt, leave it out.
- **Accuracy rule:** Cross-reference every claim against the actual CIM before including it. Do not include market-demand traits (recurring %, owner removed, AI, SOPs, clean books, low concentration) unless confirmed in the CIM.

## What Makes Agency Deals Sell (Market Demand Doc)
- **Recurring revenue** (retainer-based) → 5x–7x EBITDA vs 3x–4.5x for project-based
- **Owner removed** → systematized sells at 7x–8x vs founder-dependent at 3x–4x
- **Low client concentration** → no client >10–15%, top 3 <25% combined
- **AI-integrated operations** → 40–100% valuation premium over non-AI peers
- **Niche specialization** → accelerates sale, raises multiple
- **EBITDA margins** → 25–30%+ ideal; 50%+ crushes benchmark
- **Clean financials** → QoE analysis now standard; informal books = discount
- Always frame pricing as a discount to market comps (e.g. "1.74x vs 2.5x–3.9x market range")

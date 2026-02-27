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
- **Workflow:** Dylan provides CIM → I generate HTML deck → push to GitHub Pages → link goes in GHL iframe and Google Doc
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
- **GitHub Pages repo:** https://github.com/DylanWilson462/zkw-decks — push new decks to `/Users/george/.openclaw/workspace/slideshows/` and `git push origin main`. Each deck at `https://dylanwilson462.github.io/zkw-decks/slideshows/<filename>.html` ⚠️ MUST include `/slideshows/` in URL — without it returns 404
- **nano-banana-pro:** Gemini API key in `openclaw.json` → `models.providers.google.apiKey`. Script: `/opt/homebrew/lib/node_modules/openclaw/skills/nano-banana-pro/scripts/generate_image.py`. Save creatives to `meta-ads/creatives/` with timestamp filenames.
- **Ad formats for ZKW deal listings:** See dedicated sections below — X Post Ads (5), Note Ads (2), P&L Ad (1) = 8 total per deal.

## Completed Deal Marketing Packages

| Deal | Deck URL | Drive Folder | Status |
|------|----------|--------------|--------|
| Project Maple | https://dylanwilson462.github.io/zkw-decks/slideshows/project-maple.html | — | Ads only (no full package) |
| Project Beacon | https://dylanwilson462.github.io/zkw-decks/slideshows/project-beacon.html | https://drive.google.com/drive/folders/1iE63N3YweM5LqxT5Bkh4Cd1Xkhx7szck | ✅ Full package delivered |

## "Create Marketing Assets" — Master Workflow Trigger

**When Dylan sends a CIM + says "Create marketing assets" produce ALL of the following:**

### Step 1: Slide Deck
- Build HTML slideshow following all slide deck rules (14–16 slides, ZKW template, Anton/Montserrat fonts, etc.)
- Push to GitHub Pages repo

### Step 2: Image Ads (8 total)
- 5 × X Post Ads (dark theme, Dylan's headshot, first-person voice, Apple emoji)
- 2 × Note Ads (iPhone Notes style, stat-first + feature-first)
- 1 × P&L Ad (Instagram Story 9:16, yellow banner + table + red arrow)

### Step 3: Ad Copy
- **Primary text** — first-person hook + 3 stat lines + operator-removed line + CTA ("Tap to learn more to get deal details.")
- **3 headlines** — follow format: (1) "Monthly Recurring [profit] [descriptor] For Sale", (2) "[key feature] [descriptor] For Sale", (3) "[$/mo profit]. [key trait] Agency For Sale"
- **Description** — always: "Priced to sell fast"

### Step 4: Send for Approval
- Send all assets (slide deck link + 8 images + ad copy) to Dylan for review
- Wait for approval or revision requests

### Step 5: On Approval — Deliver to Drive
1. Create Google Doc with all ad copy (primary text, 3 headlines, description) **plus slide deck link and responsive embed code** (see embed format below)
2. Upload all 8 image ads + Google Doc to a new Google Drive folder named "[Deal Name] Ads"
3. Share folder with dylan@zastrekentwilson.com
4. Send Dylan the Drive folder link + slide deck link

**Responsive embed code to include in every Google Doc:**
```html
<div style="position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;">
  <iframe src="[DECK_URL]"
    style="position:absolute;top:0;left:0;width:100%;height:100%;border:none;"
    allowfullscreen>
  </iframe>
</div>
```

---

## Deal Ad Set — Image Ads Only Trigger

**When Dylan sends a CIM + says "make ads" (or "we're selling X, make ads"), produce ALL 8 images:**
1. 5 × X Post Ads (dark theme Twitter style)
2. 2 × Note Ads (iPhone Notes style)
3. 1 × P&L Ad (Instagram Story 9:16)

Individual ad types can also be triggered by name: "X ads", "Twitter ads", "note ads", "P&L ad."

**Copy rules applying to ALL ad types:**
- NO asking price or valuation multiple in any ad
- Extract key stats from CIM: revenue, profit/EBITDA, margin %, years in business, team size, unique differentiators
- Highlight text = the single most compelling hook from the CIM

---

## X Post Ads (Twitter Ads) — Standard Format

**Trigger:** Any time Dylan sends a CIM and says "make ads" or "we're selling X, make ads" OR asks for "X ads" or "Twitter ads."

**Output:** 5 square (750×750px) dark-mode X/Twitter post images. Always make all 5 variations.

**Profile:** Dylan Wilson · @dylanwilson · blue verified badge · headshot at `/Users/george/.openclaw/media/inbound/file_36---dd5a2d2f-713f-4ebc-9255-65e25398d221.png`

**3 Ad Formats (rotate across 5 ads):**
1. **Plain text + blue highlight** — hook stat, short line facts, one key metric in `#1d9bf0` blue, closer, CTA
2. **Green checkbox list** — hook, 5–6 ✅ bullet points (`#00ba7c` bg), closer, CTA
3. **Minimal** — hook, 2–3 punchy standalone lines, CTA

**Copy rules:**
- **VOICE: Always first-person** — written as Dylan posting about HIS deal. Start with "I'm selling..." or "We're selling..." — never third-person announcement style
- Hook = big number or surprising fact up top, in first-person framing
- NO asking price / valuation multiple in any ad
- Always end with: "Tap to learn more to get deal details."
- Timestamp: `10:18 AM · Feb 9, 2026 · **600K** Views`
- Engagement: `1.5K` comments · `1.9K` retweets · `2K` likes · `2K` bookmarks
- **Checkbox format:** Use ✅ Apple emoji (renders natively via WebKit on macOS) — NOT custom SVG circles
- **Global rule:** Always use Apple emoji across all ad formats (X Post, Note, P&L) — they render natively on macOS WebKit, no custom SVG or icon fonts needed

**Technical pipeline:**
1. Create working dir `/tmp/[deal]_ads/`, symlink playwright: `ln -sf /tmp/maple_ads/node_modules /tmp/[deal]_ads/node_modules`
2. Write HTML files to `/tmp/[deal]_ads/ad1-5.html` and `note1-2.html`
3. Key CSS: tweet `width: 750px`, background `#15202b`, font-family `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif` — **always set font-family explicitly on html/body or it breaks**
4. Embed headshot as base64 inline — `base64 -i [file] | tr -d '\n' > headshot_b64.txt` (NOT file:// URL — breaks in playwright)
5. Screenshot `.tweet` element via playwright webkit node script → raw PNGs
6. Composite each raw PNG centered onto 750×750 `#15202b` canvas: `magick -size 750x750 xc:#15202b raw.png -gravity Center -composite final.png`
7. Save finals to `/Users/george/.openclaw/workspace/[deal]_ads/` and send via `message` tool with `filePath`

**Playwright node_modules location:** `/tmp/maple_ads/node_modules` — symlink to new deal dir to reuse.

**Reference files** (working examples): `/Users/george/.openclaw/workspace/maple_ads/ad1_final.png` through `ad5_final.png`

## Note Ads (iPhone Notes Style) — Standard Format

**Trigger:** Any CIM + "make ads" / "we're selling X, make ads" OR asks for "note ads." Always make BOTH variations.

**Output:** 2 square (750×750px) white-background iPhone Notes app style images.

**2 Ad Variations:**
1. **Stat-first** — lowercase title leading with the biggest financial hook (e.g. "CA$640K/yr profit, retainer-based digital marketing agency for sale")
2. **Feature-first** — Title Case title describing business characteristics (e.g. "Digital Marketing Agency With 74% Profit Margins & Zero Paid Marketing For Sale")

**Both variations share identical:**
- iOS Notes chrome bar (back `‹` button left, 3 icon buttons right)
- Date: `February 9, 2026 at 10:08 AM` — small grey centered
- Bullet list with en dashes `–`, key words **bolded**
- CTA: `Tap below for full P&L and deal structure`
- Background: `#ffffff`
- Font: `-apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Helvetica Neue", Arial, sans-serif`

**Copy rules:**
- Title: 40px, weight 800, `#111111`, line-height 1.13
- Bullets: 19px, weight 400, `#1a1a1a`, en dash `–`, key phrases bold
- CTA: 19px, weight 400
- No asking price unless deal explicitly requires it

**Technical pipeline (identical to X Post Ads):**
1. Write HTML to `/tmp/[deal]_ads/note1.html` and `note2.html`
2. Screenshot `.note` element via playwright node script → raw PNGs
3. Composite centered onto 750×750 `#ffffff` canvas: `magick -size 750x750 xc:#ffffff raw.png -gravity Center -composite final.png`
4. Copy to `/Users/george/.openclaw/workspace/[deal]_ads/` and send via `message` tool

**Reference files:** `/Users/george/.openclaw/workspace/maple_ads/note1_final.png` and `note2_final.png`

---

**Full ad set per deal = 8 images total:**
- 5 × X Post Ads (dark theme, Dylan's headshot)
- 2 × Note Ads (white, iPhone Notes style)
- 1 × P&L Ad (see P&L Ads section)

## P&L Ads — Standard Format

**Trigger:** Any CIM + "make ads" / "we're selling X, make ads" OR asks for "P&L ads." Make 1 per deal.

**Output:** Single Instagram Story portrait image (9:16 ratio, 1080×1920px equivalent).

**Layout (top to bottom):**
1. **Yellow banner** — `#FFE500`, rounded rect, bold Arial Black text with the top highlight (e.g. "16+ Year Retainer-Based Agency With 74% Profit Margins")
2. **P&L header** — centered bold text: "Profit & Loss Statement / For the Year Ended 31 December [YEAR]"
3. **P&L table** — dark navy `#1E3A5F` header row (white text: "P&L (CAD/USD)" left, year right), thin grey borders, left-aligned labels, right-aligned numbers. Bold rows: Gross Profit, EBITDA (Before Add-Backs), Adjusted EBITDA, Seller's Disc. Earnings (SDE)
4. **Red diagonal arrow** — `#E8192C`, diagonal from lower-left area pointing up-right to the SDE value. Shaft = 2× head length. Fully inside the image. Does NOT cover the SDE label text on the left.

**Standard P&L rows:**
- Revenues | [amount]
- Gross Profit (bold) | [amount]
- Operating Expenses | ([amount])
- EBITDA (Before Add-Backs) (bold) | [amount]
- Personal Expense Add-Backs | [amount]
- Adjusted EBITDA (bold) | [amount]
- Operator Draws | [amount or 0]
- Seller's Disc. Earnings (SDE) (bold) | [amount]

**No asking price in the table.**

**Technical pipeline:**
1. Generate base image with nano-banana-pro (2K resolution) using the prompt template below — no arrow in prompt
2. Use Python + Pillow to draw the arrow programmatically with exact coordinates

**Nano-banana base prompt template:**
```
"Create a clean Instagram Story ad (9:16 portrait, white background).
TOP: Bright yellow (#FFE500) rounded rectangle banner, bold black Arial Black text: '[HIGHLIGHT]'
MIDDLE: Centered bold black text 'Profit & Loss Statement' and 'For the Year Ended 31 December [YEAR]'
Then a clean financial table: dark navy blue (#1E3A5F) header row, white text 'P&L (CAD)' left-aligned, '[YEAR]' right-aligned, thin grey borders, left-aligned labels, right-aligned numbers. Bold rows: Gross Profit, EBITDA (Before Add-Backs), Adjusted EBITDA, Seller's Disc. Earnings (SDE).
Rows: [list all rows]. No red arrow — clean table only."
```

**Python arrow script** (run after nano-banana generates base image — auto-detects SDE row position):
```python
import math
from PIL import Image, ImageDraw

img = Image.open("base.png")
w, h = img.size
pixels = img.load()
draw = ImageDraw.Draw(img)

# --- Auto-detect navy header row ---
navy_rows = []
for y in range(0, h, 2):
    count = sum(1 for x in range(0, w, 10)
                if pixels[x,y][0]<60 and pixels[x,y][1]<90 and pixels[x,y][2]>80)
    if count > (w/10)*0.3:
        navy_rows.append(y)

header_bottom = max(navy_rows)

# --- Auto-detect table bottom (last grey border line) ---
grey_rows = []
for y in range(header_bottom+5, h, 2):
    count = sum(1 for x in range(0, w, 10)
                if abs(int(pixels[x,y][0])-int(pixels[x,y][1]))<15
                and abs(int(pixels[x,y][1])-int(pixels[x,y][2]))<15
                and 160 < pixels[x,y][0] < 220)
    if count > (w/10)*0.6:
        grey_rows.append(y)

table_bottom = max(grey_rows)
row_h = (table_bottom - header_bottom) / 8
sde_y = int(header_bottom + 7.5 * row_h)
tip_x = int(w * 0.92)

# Erase only below table bottom
draw.rectangle([0, table_bottom + 5, w, h], fill=(255, 255, 255))

print(f"Table bottom: {table_bottom}, SDE y: {sde_y}, Tip: ({tip_x},{sde_y})")

# --- Draw arrow ---
angle_rad = math.radians(38)
dx, dy = math.cos(angle_rad), -math.sin(angle_rad)
px, py = math.sin(angle_rad),  math.cos(angle_rad)

head_len  = int(w * 0.195)
shaft_len = int(w * 0.391)   # shaft = 2x head
body_half = int(w * 0.047)
head_half = int(w * 0.090)

tip_y = sde_y
hx = tip_x - head_len*dx;  hy = tip_y - head_len*dy
tx = tip_x - (head_len+shaft_len)*dx;  ty = tip_y - (head_len+shaft_len)*dy

def pt(cx,cy,pax,pay,off): return (cx+off*pax, cy+off*pay)
polygon = [
    pt(tx,ty,px,py, body_half), pt(hx,hy,px,py, body_half),
    pt(hx,hy,px,py, head_half), (tip_x, tip_y),
    pt(hx,hy,px,py,-head_half), pt(hx,hy,px,py,-body_half),
    pt(tx,ty,px,py,-body_half),
]
draw.polygon(polygon, fill=(232,25,44))
img.save("output.png")
```
**Venv:** `python3 -m venv /tmp/arrowenv && /tmp/arrowenv/bin/pip install pillow -q`
**Run:** `/tmp/arrowenv/bin/python3 arrow.py`
**Reference file:** `/Users/george/.openclaw/workspace/maple_ads/pnl_arrow_final.png`

---

**Full ad set per deal = 8 images total:**
- 5 × X Post Ads (dark theme, Dylan's headshot)
- 2 × Note Ads (white, iPhone Notes style)
- 1 × P&L Ad (Instagram Story 9:16, yellow banner + table + diagonal red arrow)

## Google Drive & Docs API

**⚠️ gog CLI hangs indefinitely — do NOT use for Drive/Docs operations. Use Python + Drive API directly.**

- **Credentials:** Client ID + Secret in `~/Library/Application Support/gogcli/credentials.json`
- **Tokens:** `~/Library/Application Support/gogcli/tokens.json` → key: `dylan@zastrekentwilson.com`
- **Refresh token flow:** POST to `https://oauth2.googleapis.com/token` with `grant_type=refresh_token`
- **Upload file to Drive:** multipart POST to `https://www.googleapis.com/upload/drive/v3/files?uploadType=multipart`
- **Create Google Doc from text:** same multipart upload with `mimeType: application/vnd.google-apps.document` in metadata + `text/plain` body — Drive auto-converts
- **Append to Doc:** GET doc to find end index → `POST /v1/documents/{id}:batchUpdate` with `insertText` request
- **Create folder:** POST to Drive files API with `mimeType: application/vnd.google-apps.folder`
- **Share:** POST to `https://www.googleapis.com/drive/v3/files/{id}/permissions` with `{type:user, role:reader, emailAddress:...}`
- **Reference script:** `/tmp/beacon_drive.py` (full working example with all operations)
- **Share target:** always `dylan@zastrekentwilson.com`

## What Makes Agency Deals Sell (Market Demand Doc)
- **Recurring revenue** (retainer-based) → 5x–7x EBITDA vs 3x–4.5x for project-based
- **Owner removed** → systematized sells at 7x–8x vs founder-dependent at 3x–4x
- **Low client concentration** → no client >10–15%, top 3 <25% combined
- **AI-integrated operations** → 40–100% valuation premium over non-AI peers
- **Niche specialization** → accelerates sale, raises multiple
- **EBITDA margins** → 25–30%+ ideal; 50%+ crushes benchmark
- **Clean financials** → QoE analysis now standard; informal books = discount
- Always frame pricing as a discount to market comps (e.g. "1.74x vs 2.5x–3.9x market range")

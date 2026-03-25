# Glossary — Sunstone REA

## Property Types
- **MHP** — Mobile Home Park / Manufactured Housing Park
- **MHC** — Manufactured Home Community (same asset class, more formal label)
- **RV Park** — Recreational Vehicle Park
- **Mixed-use** — MHP + RV combination

## Deal Terms
- **OM** — Offering Memorandum (the deal marketing package sent to buyers)
- **NDA / CA** — Non-Disclosure Agreement / Confidentiality Agreement (signed before OM is released)
- **LOI** — Letter of Intent
- **PSA** — Purchase and Sale Agreement
- **UC** — Under Contract
- **Comp** — Comparable sale (logged in Salesforce as TTL_Core__Comp__c)
- **Listing** — A property being marketed for sale
- **Portfolio** — Multiple properties sold as a single deal

## Deal Pipeline Stages
1. Proposal → 2. Marketing (active listing) → 3. Under Contract → 4. Closed

## Platforms & Tools
- **REthink** — CRE-focused Salesforce CRM (namespace: TTL_Core__)
- **BuildOut** — Listing platform integrated with Salesforce (syncs listing data)
- **Egnyte** — Cloud file storage for all deal documents
- **KOA** — Kampgrounds of America (franchise brand for RV/camp properties)

## PDF → Markdown Tools

- **liteparse** (`@llamaindex/liteparse`) — **preferred for OMs, rent rolls, T-12s, and any tabular PDF**. Preserves spatial/column layout; keeps label+value on same line. Install: `npm i -g @llamaindex/liteparse --prefix ~/.npm-global`. Use `--no-ocr` for digital PDFs (required in sandbox — tesseract.js can't fetch models offline). CLI: `lit parse file.pdf --no-ocr -o out.txt`
- **pymupdf4llm** — fallback for scanned/image-based PDFs where liteparse OCR can't run
- **markitdown** — fine for prose-heavy docs (bios, narratives, location sections) where table fidelity doesn't matter
- **opendataloader-pdf** — untested contender; strong table detection, 80+ language OCR. Evaluate if liteparse falls short.

## People Shorthand
- **Bob** = Robert Whittaker (broker, Sunstone REA)
- **Don** = Don Vedeen (Jared's partner)
- **Cheyenne** = Cheyenne Whittaker (back office lead, runs deal pipeline + Monday meetings)
- **Brad** = Bradley Levine (analyst)
- **Stefen** = Stefen Krizsa (analyst)
- **Christian** = Christian Aznar (SVP of Underwriting, analyst team lead)
- **Casey** = Casey Thom (broker)

## Business Metrics
- **BOV** = Broker Opinion of Value — valuation/pitch deck presented to sellers to win listing assignments
- **Gross fees** = commission/fee revenue earned on closed deals
- **Assignment** = winning the right to list and market a property
- **Back office** = Cheyenne's team — transaction coordination, pipeline management, admin

## Previous Firm
- **Northmarq** = prior firm (National Manufactured Housing Group) — Jared and Don's shop before Sunstone REA
- **MHI** = Manufactured Housing Institute (trade org; gives annual Excellence Awards)
- **Sun Communities** = major MHP REIT — institutional buyer, purchased deals from Jared's team

## Known Acronyms in Deal Names
- **RHP** — Large MHP portfolio owner/operator (multiple deal portfolios)
- **OCTA** — Development deal client
- **NW** — Northwest (as in NW Ohio Portfolio)
- **MSA** — Metropolitan Statistical Area (e.g., Charlotte NC MSA)
- **NYS** — New York State (Teton NYS MHC Portfolio)

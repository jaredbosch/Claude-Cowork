# Memory

## Me
**Jared Bosch** (`jbosch@sunstonerea.com`) — Director / Broker at Sunstone REA

## Company
**Sunstone REA** — MHP/RV Park brokerage firm formed by a PE group merging two boutique brokerages: legacy Sunstone and OtherStreet. Jared and Don Vedeen were also recruited by the PE group. Everyone now operates under the Sunstone REA banner.
- CRM: REthink (Salesforce, TTL_Core__ namespace) + BuildOut integration
- Files: Egnyte → /Shared/Brokerage/
- Email: Outlook

## People — Sunstone REA

| Who | Role |
|-----|------|
| **Jim Fletcher** | Managing Director |
| **Allison Weiss** | Team (aweiss@sunstonerea.com) |
| **Ian Keith** | Team (ian@sunstonerea.com) |
| **Don Vedeen** | Director / Broker — Jared's partner (don@sunstonerea.com) |
| **Hanna LeCavalier** | Team (hanna@sunstonerea.com) |
| **Bradley Levine** | Team (bradley@sunstonerea.com) |
| **Zach Sheck** | Team (zach@sunstonerea.com) |
| **Paul Weiss** | CEO (pweiss@sunstonerea.com) |
| **Jo Plummer** | Team (jo@sunstonerea.com) |
| **Kolman Bubis** | Team (kolman@sunstonerea.com) |
| **Stefen Krizsa** | Team (stefen@sunstonerea.com) |
| **Casey Thom** | Executive Managing Director (cthom@sunstonerea.com) |
| **Hudson Bird** | Team (hudson@sunstonerea.com) |
| **Bob McBroom** | Executive Managing Director (robert@sunstonerea.com) |
| **Jacob Anderson** | Team (jacob@sunstonerea.com) |
| **Jeff Kozel** | Team (jeff@sunstonerea.com) |

## People — OtherStreet (legacy firm, now merged into Sunstone REA)

| Who | Role |
|-----|------|
| **Enon Winkler** | Managing Partner |
| **Russ Williamson** | Managing Partner |
| **Brett Garner** | Vice President |
| **Ben Cohen** | Director |
| **Robert Whittaker** | Director |
| **Christian Aznar** | SVP of Underwriting |
| **Cesar Ovando** | Advisor |
| **Cheyenne Whittaker** | Transaction Coordinator |
| **Doug Klein** | Team |

## Terms

| Term | Meaning |
|------|---------|
| MHP | Mobile Home Park / Manufactured Housing Park |
| MHC | Manufactured Home Community (same as MHP, more formal) |
| RV Park | Recreational Vehicle Park |
| OM | Offering Memorandum (the deal marketing package) |
| NDA | Non-Disclosure Agreement (signed before receiving OM) |
| UC | Under Contract |
| LOI | Letter of Intent |
| PSA | Purchase and Sale Agreement |
| CA | Confidentiality Agreement (same as NDA) |
| TTL_Core | REthink CRM Salesforce namespace |
| BuildOut | Listing syndication platform integrated with Salesforce |
| KOA | Kampgrounds of America (franchise RV/campground brand) |

## Deal Pipeline Structure (Egnyte)

| Stage | Folder |
|-------|--------|
| Proposals | `/Shared/Brokerage/1. Proposals` |
| Active Listings | `/Shared/Brokerage/2. Marketing` |
| Under Contract | `/Shared/Brokerage/3. Under Contract` |
| Closed | `/Shared/Brokerage/4. Closed Deals` |
| Templates | `/Shared/Brokerage/5. Templates` |
| Admin | `/Shared/Brokerage/6. Administrative Docs` |
| Marketing Assets | `/Shared/Brokerage/7. Marketing Docs` |

## Salesforce Key Objects (REthink)

| Object | Label |
|--------|-------|
| TTL_Core__Property__c | Property |
| TTL_Core__Deal__c | Deal Pipeline |
| TTL_Core__Comp__c | Comp (listing comparable) |
| TTL_Core__Offer__c | Offer |
| TTL_Core__Prospect__c | Inquiry / Requirement |
| TTL_Core__Associated_Party__c | Associated Party |
| TTL_Core__Invoice__c | Invoice |

## Cowork Folder Structure

```
Cowork/
├── CLAUDE.md              ← system (do not move)
├── TASKS.md               ← task tracking (do not move)
├── memory/                ← persistent context (do not move)
├── brand/                 ← brand assets (do not move)
│
├── deals/                 ← one subfolder per deal (e.g. deals/risinger-ridge/)
│   └── [deal-name]/       ← source OMs, call notes, deal-specific context
│
└── outputs/               ← all deliverables, sorted by type
    ├── market-research/   ← market analysis reports (MD + PDF)
    ├── flyers/            ← deal flyers (PDF)
    ├── comps/             ← listing and rental comps (PDF, XLSX)
    ├── proposals/         ← listing proposals (PDF)
    ├── bov/               ← broker opinion of value / underwriting models (XLSX)
    │   └── [deal-name]/   ← one subfolder per deal (e.g. bov/city-view-spartanburg/)
    └── other/             ← anything else (dashboards, reviews, etc.)
```

**Save rules (always follow these):**
- Never save outputs to Cowork root — always a subfolder
- Client-facing deliverables → `outputs/[type]/`
- Deal source files / notes → `deals/[deal-name]/`
- Temp/junk files → delete, never leave in root

## Preferences
- Casual, direct communication
- British English spelling
- Responses: concise unless depth needed
- All client-facing deliverables (flyers, OMs, proposals) → PDF by default, never PPTX/DOCX
- When converting a doc to markdown, always save as a .md file and link it — never dump raw output into chat unless explicitly asked
- When instruction is "show me X", show X only — no unsolicited summaries or editorialising
- pdf-to-markdown skill script is missing; use pymupdf4llm directly (markitdown works better for clean digital PDFs, pymupdf4llm for scanned)

## Design / Brand Rules
- Always read `brand/BRAND.md` before starting any client-facing deliverable (deck, flyer, OM, proposal)
- Official Sunstone brand colors: Sunburst `#FB8B0D`, Charcoal `#303030`, Slate `#6C7983`, Ivory `#EEEBE4`
- Brand font: Montserrat Medium (body copy) — not Calibri
- BOV deck headers: never pass rightLine text params — logo collision risk. Title only.

## Salesforce Data Rules
- If SF site/unit count conflicts with verbal intel from call notes, flag the discrepancy before using either — don't silently pick one
- Multiple property records with same owner + city + zip = likely duplicates/same park; surface this ambiguity before treating as separate assets

## Listing Comp Skill Overrides
- **Listed_Date__c**: Always populate with today's date (YYYY-MM-DD) when creating a `TTL_Core__Comp__c` record. Assume listing date = date added unless the OM explicitly states otherwise. This ensures the field is always populated for future filtering.

## Self-Improvement System
Files live in `memory/self-improvement/`. Read and update these as part of continuous improvement.

| File | Purpose |
|------|---------|
| `mistakes.md` | Log of errors — what went wrong, why, and the corrective rule |
| `lessons.md` | Generalised rules extracted from mistakes; pattern detection table |
| `soul.md` | Foundational behavioural principles (unconditional) |
| `playbook.md` | Proven workflows and strategies to reuse |

**Rules:**
- Log any mistake to `mistakes.md` immediately after it's identified
- Extract lesson → `lessons.md`; promote to `soul.md` if foundational
- If 3+ mistakes share a root cause, write a higher-order rule in `lessons.md#pattern-watch`
- If a better workflow is discovered, document it in `playbook.md`

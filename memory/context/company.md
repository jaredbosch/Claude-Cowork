# Sunstone REA — Company Context

## What They Do
MHP and RV Park brokerage. Brokers (Directors) work the full deal cycle:
1. **Win listings** — pitch sellers, get the listing agreement signed
2. **Market** — produce the OM, push to buyers nationwide
3. **Get offers** — qualify buyers, drive LOIs
4. **Close** — negotiate, manage PSA through to closing

Represent sellers (and sometimes buyers) in the sale of:
- Manufactured Housing Parks (MHP / MHC)
- RV Parks
- Mixed-use MH+RV properties
- Development land deals (via OCTA)
- Large portfolios (multiple parks sold as a package)

## Tech Stack
- **Salesforce** (REthink CRM — TTL_Core__ namespace)
  - Properties, Deals, Comps, Offers, Contacts, Invoices
  - BuildOut connector for listing syndication
- **Egnyte** — all deal files
- **Outlook** — email
- **BuildOut** — listing platform (synced to Salesforce)

## Egnyte File Structure
```
/Shared/Brokerage/
  0. NEW DEAL TEMPLATE - Property Name - City, State
  1. Proposals/
  2. Marketing/          ← active listings (~44 deals)
  3. Under Contract/     ← deals in escrow (~32 deals)
  4. Closed Deals/
  5. Templates/
  6. Administrative Docs/
  7. Marketing Docs/
```

## Deal Naming Convention
`[Property Name] - [City, State]` or `[Seller Name] Portfolio` for multi-park deals

## Key Repeat Clients/Sellers
- **RHP** — large national MHP operator, multiple portfolio deals
- **OCTA** — development project client
- **Park Place Communities**
- **Abraham Anderson** (Indiana)
- **Behn Wilson**
- **Teitelbaum**
- **Gallagher & Baldwin** (Northeast)
- **Teton** (NY)
- **Feliz Home Communities** (Alabama)

## Pipeline Snapshot (as of early 2026)
- ~44 active marketing deals
- ~32 deals under contract

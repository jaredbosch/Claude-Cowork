# Claude-Cowork Backup

Version-controlled backup of Jared's Cowork brain — memory, instructions, and context files.

## What's Here

| Path | Purpose |
|------|---------|
| `CLAUDE.md` | Master system instructions — preferences, rules, folder structure, SF rules |
| `TASKS.md` | Active task tracker |
| `brand/BRAND.md` | Sunstone brand reference (colours, fonts, logos, Egnyte paths) |
| `memory/context/` | Who I am, how I work, company context, brand voice |
| `memory/deals/` | Deal-specific intelligence (e.g. Project Cloudbreak) |
| `memory/people/` | Team rosters — Sunstone REA + OtherStreet |
| `memory/glossary.md` | Industry/internal terminology |
| `memory/self-improvement/` | Lessons, mistakes log, playbook, soul principles |
| `linq-best-practices.md` | iMessage / Linq outreach best practices |

## What's NOT Here

Binary files (PDFs, XLSX, PPTX, images) are gitignored — back those up via Egnyte.

## Backup Workflow

I update this repo whenever the brain files change. For manual backup:

```bash
git add .
git commit -m "Cowork backup - $(date +%Y-%m-%d)"
git push
```

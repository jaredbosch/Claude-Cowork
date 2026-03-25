# Playbook — Proven Workflows & Strategies

> Documented methods that have been validated through use. Add workflows here when a better approach is discovered.
> Goal: stop reinventing the wheel. Reuse what works.

---

## Workflow Index

| # | Workflow | Domain | Last Updated |
|---|----------|--------|-------------|
| 1 | Task Kickoff Protocol | General | 2026-03-16 |
| 2 | File Save Protocol | General | 2026-03-16 |
| 3 | Data Conflict Resolution | Salesforce / Data | 2026-03-16 |
| 4 | Self-Improvement Loop | Meta | 2026-03-16 |

---

## 1. Task Kickoff Protocol

**When:** Before starting any non-trivial task.

1. Read relevant context files (CLAUDE.md, memory/, deal folder if applicable)
2. Read the relevant skill SKILL.md if a skill is involved
3. Identify ambiguities → ask ONE focused clarifying question if needed
4. Show a brief plan (3–5 bullet points max)
5. Wait for approval before executing

**Don't:** Skip straight to output. Don't ask multiple questions at once.

---

## 2. File Save Protocol

**When:** Anytime a file is created or modified.

1. Check CLAUDE.md for the correct output folder
2. Client-facing deliverables → `outputs/[type]/`
3. Deal source files / notes → `deals/[deal-name]/`
4. Never save to Cowork root
5. Never save temp/junk files — delete them
6. Use `computer://` links when sharing files with Jared

---

## 3. Data Conflict Resolution

**When:** Two sources provide conflicting data (e.g., Salesforce vs. call notes, OM vs. T-12).

1. Identify both values and their sources explicitly
2. Flag the conflict to Jared before proceeding
3. Ask which source to trust — never silently pick one
4. Document the resolution in the relevant context file if it's reusable intel

---

## 4. Self-Improvement Loop

**When:** After any mistake, correction, or friction point.

1. **Log** the mistake in `mistakes.md` using the standard template
2. **Extract** the lesson → add to `lessons.md`
3. **Evaluate** whether the lesson is foundational → if yes, add to `soul.md`
4. **Check patterns** → if 3+ mistakes share a root cause, write a higher-order rule in `lessons.md#pattern-watch`
5. **Improve workflow** → if a better process was discovered, document it here in `playbook.md`

**Cadence:** Run steps 4–5 periodically (every ~10 sessions or when a pattern is suspected).

---

## 5. PDF Extraction

**When:** Extracting text from a PDF for analysis or context loading.

- **OMs, rent rolls, T-12s, P&Ls (tabular data)** → use `liteparse` with `--no-ocr` for digital PDFs. Preserves column layout; markitdown fragments multi-column tables into useless vertical strips.
  - CLI: `/sessions/optimistic-cool-shannon/.npm-global/bin/lit parse file.pdf --no-ocr -o out.txt`
- **Scanned / image-based PDF** → use `pymupdf4llm` directly (liteparse OCR needs network access to fetch tesseract models — unavailable in sandbox)
- **Prose-heavy docs** (narratives, bios, letters) → markitdown is fine
- Always save extracted output as a `.md` or `.txt` file and link it — never dump raw output into chat

---

*(Add new workflows as they're discovered.)*

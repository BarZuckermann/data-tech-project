# CLAUDE.md — Covered AI (SmartWarranty AI)

A student project for the Data & Technology course. Covered AI is a mobile app for family households: it digitizes warranty receipts, tracks expiration dates, and uses an AI assistant to judge whether a defect is covered and to draft a claim letter.
Authors: Shira Rahamim, Bar Zuckermann, Noa Roash.

The repository is public on GitHub: `BarZuckermann/data-tech-project`.

## Branches

- `main`: the stable, approved version. Don't work on it directly.
- `dev`: day-to-day work. New changes are committed here and merged into `main` only after the user approves.

## Files

| File | Contents |
|---|---|
| `Covered-AI-PRD.md` | The full PRD and the product's source of truth: problem, KPIs, MVP scope, business, and the screen spec (section 6) |
| `Covered-AI-Stitch-Screens.md` | Detailed spec of the 7 screens in Stitch, sample data, user flow, and each screen's ID and status |
| `stitch-screens/` | PNG of each screen (0–6), named `<number>-<name>.png` |

## Working rules

- **All project files are saved in this folder**, even when the session opens in another directory (for example `שיטות מחקר`, which is unrelated).
- If the PRD changes, update `Covered-AI-PRD.md`, then check whether `Covered-AI-Stitch-Screens.md` and the Stitch screens need updating too.
- Every screen change in Stitch gets recorded in the status table of `Covered-AI-Stitch-Screens.md`.
- The user writes in Hebrew, so reply in Hebrew. Project documents stay in English.
- Commit and push only on request. The repository is public, so don't commit secrets or private details beyond the authors' names.

## MVP scope (don't add beyond it without approval)

- Fast ingestion: camera, upload (PDF/JPG/PNG) or manual entry, then an editable verification card.
- Expiration reminders 30 days and 7 days before expiry.
- AI assistant: a coverage verdict plus a claim letter with **copy to clipboard only**. Phase 1 has no email sending, mailbox integration or PDF export.
- A mandatory legal disclaimer: the app is informational only, not legal advice, and claim letters and verdicts are drafts.

## Stitch

- Project: `3613266149126041490` — https://stitch.withgoogle.com/projects/3613266149126041490
- Design system "Covered AI": `assets/3490380447981590931`. Primary `#2F5D50` (sage), canvas `#F7F7F5`, Manrope for headlines, Inter for body text, 12px radius, pill-shaped buttons and badges, light mode, mobile.
- Status badges: Active is green, ≤30 days is amber, ≤7 days or expired is muted red, archived is gray.
- **Keep sample data consistent across all screens.** The demo item is the Dyson V15 Detect: Model SV47, Serial D15-8X2K-4471, bought at Electronics Hub on Dec 2, 2024, 24-month warranty ending Dec 2, 2026, 18 days left. Other items: MacBook Air M3 (5 days left), Nespresso Vertuo (26 days), Samsung Refrigerator, Bosch Cordless Drill (Active), LG OLED TV (Expired).

### Technical notes for the Stitch MCP

- Screenshot and HTML `downloadUrl` values need authentication (they return 401). Use `download_file` with the file's `name` instead.
- `download_file` returns an image as base64 inside JSON and is usually too large to show inline, so decode it with PowerShell (`[Convert]::FromBase64String`). Python isn't installed on this machine.
- `generate_screen_from_text` can time out but still finish. Don't retry; run `list_screens` first.
- `edit_screens` applies DOM edits, but the saved HTML and screenshot may not update right away. Ask the user to confirm the change in the Stitch editor.

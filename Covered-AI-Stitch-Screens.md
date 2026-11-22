# Covered AI (SmartWarranty AI) — Stitch Screen Designs

**Authors:** Shira Rahamim, Bar Zuckermann, Noa Roash
**Stitch project:** [Covered AI (SmartWarranty AI)](https://stitch.withgoogle.com/projects/3613266149126041490) — project ID `3613266149126041490`
**Generated:** 2026-11-15 · Device: Mobile · UI language: English

---

## Design System — "Covered AI"

| Token | Value |
|---|---|
| Mode | Light |
| Primary | `#2F5D50` (deep sage green) |
| Neutral canvas | `#F7F7F5` (warm gray) |
| Headline font | Manrope |
| Body / label font | Inter |
| Corner radius | 12px (cards), pills for badges and buttons |
| Color variant | Neutral |

**Design principles (from PRD §6):** progressive disclosure, generous negative space, neutral palette, low cognitive load, one primary action per screen, thin line icons, white cards with soft shadows.

**Warranty status badges**

| Status | Color |
|---|---|
| Active | Green |
| Expiring ≤ 30 days | Amber |
| Expiring ≤ 7 days / Expired | Muted red |
| Archived | Gray |

---

## Screens

### Screen 0 — Legal Terms & Onboarding Gate
- Covered AI logo (sage shield with checkmark) and the headline "Before you start".
- A centered card with three points:
  1. **Informational tool only.** No legal advice.
  2. **Scans may contain errors.** Double-check extracted dates and details.
  3. **You stay in charge.** Claim letters and verdicts are drafts; dealing with merchants and repair centers is the user's responsibility.
- Acknowledgment checkbox: "I understand and agree to the Terms of Use".
- The **Get Started** button stays disabled until the box is checked.

### Screen 1 — Home Dashboard (Minimalist Hub) ✅ confirmed
- Top bar: logo · notification bell with unread dot · AI assistant shortcut.
- Amber banner: "2 items expire within 30 days" with a **Review →** link.
- "My Vault · 5 items" card feed. Each card shows only name, purchase date and status badge:

| Item | Purchased | Badge |
|---|---|---|
| Samsung Refrigerator | Mar 12, 2025 | Active |
| Dyson V15 Vacuum | Dec 2, 2024 | 18 days left |
| MacBook Air M3 | Nov 20, 2024 | 5 days left |
| Bosch Cordless Drill | Jun 8, 2025 | Active |
| LG OLED TV | Jan 15, 2023 | Expired |

- Centered floating sage **+** button, plus a bottom nav bar (Home, Items, Claims, Settings).
- Screen ID: `022ea8fb22a54d7e91cb5752cde5347a`

### Screen 2 — Ingestion Trigger Sheet
- The dashboard is dimmed under a scrim, with a bottom sheet titled "Add an item".
- Three options:
  1. 📷 **Capture Receipt**: snap a photo with the camera.
  2. ⬆️ **Upload Document or Image**: PDF / JPG / PNG.
  3. ✏️ **Manual Entry**: for items without a receipt.
- **Cancel** text button.

### Screen 3 — Scan Preview & Data Verification
- **Top half:** zoomable photo of the receipt with the extracted fields highlighted and an "Auto-filled from scan – please check" chip.
- **Bottom half:** prefilled editable fields:
  - Product Name: *Dyson V15 Detect Vacuum*
  - Brand / Manufacturer: *Dyson*
  - Purchase Date: *Dec 2, 2024*
  - Warranty Duration (months): *24*
- Primary **Save to Vault** button and a secondary **Retake photo** link.

### Screen 4 — Product Master Detail View
- Header: product image, name, brand chip, amber "Expires in 18 days" badge.
- Coverage countdown card with a progress bar ("Warranty ends Dec 2, 2026").
- Details: Brand · Model (SV47) · Serial (D15-8X2K-4471) · Purchase date · Store · Warranty term.
- Receipt thumbnail that opens the full-resolution image.
- Edit / Archive / Delete actions.
- **Focal card:** "Something wrong with this item?" with an **Ask AI Assistant** button.

### Screen 5 — Expiration Reminders Drawer
- A modal drawer titled "Expiring soon", grouped by threshold:
  - **Within 7 days:** MacBook Air M3 (5 days left)
  - **Within 30 days:** Dyson V15 (18 days), Nespresso Vertuo (26 days)
- Each row has a **View details** button and a **Check coverage** (AI) button.
- Footer: "We'll remind you 30 and 7 days before each warranty ends."

### Screen 6 — Warranty AI Assistant & Claim Drafter
- Product context chip: Dyson V15 Detect · purchased Dec 2, 2024 · 24-month warranty · 18 days left.
- User: *"The battery dies after 5 minutes and the motor makes a clicking sound."*
- AI verdict card: green **Likely covered** pill with a plain-language explanation.
- **Draft claim letter** card addressed to Dyson Customer Service / Importer, with a formal letter preview.
- **Copy to clipboard** button and an **Edit draft** link (no email sending in Phase 1).
- Disclaimer: "AI-generated draft, not legal advice."
- Message input: "Describe the problem…"

---

## User Flow

```
Screen 0 (Legal gate) ──accept──▶ Screen 1 (Dashboard)
Screen 1 ── "+" ──▶ Screen 2 (Ingestion sheet) ── Capture/Upload ──▶ Screen 3 (Verify) ── Save ──▶ Screen 1
Screen 1 ── tap item ──▶ Screen 4 (Detail) ── Ask AI ──▶ Screen 6 (AI Assistant)
Screen 1 ── bell ──▶ Screen 5 (Reminders) ── View details ──▶ Screen 4
                                          └─ Check coverage ──▶ Screen 6
```

---

## Generation Status (checked 2026-11-22)

All 7 screens exist in the Stitch project. Each screenshot was reviewed against the spec above.

| Screen | Screen ID | Status |
|---|---|---|
| 0 — Legal Terms & Onboarding Gate | `2df0cd4028504cce836898a08ae082b5` | ✅ Matches spec (checkbox + disabled Get Started) |
| 1 — Home Dashboard | `022ea8fb22a54d7e91cb5752cde5347a` | ✅ Matches spec |
| 2 — Ingestion Trigger Sheet | `a6a261be971b497b897041aba5e6075c` | ✅ Matches spec |
| 3 — Scan Preview & Data Verification | `8546be0c10624511a5a29e7687069ff5` | ✏️ Edit sent: receipt changed to Electronics Hub / DEC 02, 2024 / Model SV47 / Serial D15-8X2K-4471 so it matches Screen 4 (it had shown Best Buy, 02/12/2024 and a different serial) |
| 4 — Product Master Detail View | `35ec7deabcf04d36a39e700b302c59f6` | ✅ Matches spec |
| 5 — Expiration Reminders Drawer | `0ba6e6367fd9480ba2861f180b37209a` | ✏️ Edit sent: subtitle no longer mentions "renew coverage" (out of MVP scope) |
| 6 — Warranty AI Assistant & Claim Drafter | `0ac707d81e9246d3a77b464a9e10fe28` | ✏️ Edit sent: removed "Send Email" / "Export PDF" (PRD Phase 1 has no mailbox integration; copy only), removed "98% match", fixed overlapping fade caption |

**Local screenshots:** [`stitch-screens/`](stitch-screens/) contains a PNG of each screen, taken 2026-11-22 *before* the ✏️ edits.

**To confirm the ✏️ edits:** Stitch accepted all three (the project update time changed), but the saved HTML and screenshots still showed the old versions afterward. Open the project in Stitch. If a change isn't visible there, reapply it from the screen's notes in this table.

Other assets in the project: a shield logo (`681f4bb9418d48968389defb0188af1f`), a vacuum product photo (`5bf6956f701249f7a16f1ac209bf146b`) and a clickable prototype, "Covered AI Warranty & Item Vault" (`23247aaadd2b4921a57dd92fd6861e92`).

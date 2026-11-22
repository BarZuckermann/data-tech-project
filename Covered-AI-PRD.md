# Covered AI (SmartWarranty AI) — Product Requirements Document (PRD) & UI/UX Blueprint

**Authors:** Shira Rahamim, Bar Zuckermann, Noa Roash

> Screen designs and their generation status: [Covered-AI-Stitch-Screens.md](Covered-AI-Stitch-Screens.md)

---

## 1. Problem Definition, Target Audience & Core Value Proposition

Modern consumer electronics, household appliances, and tools are routinely accompanied by paper invoices and warranty certificates. Thermal paper receipts degrade and fade within months, while physical invoices are routinely mislaid across household drawers. Concurrently, manufacturer warranty documentation is dense, ambiguous, and printed in fine print, inducing severe cognitive fatigue whenever an appliance fails. Consequently, consumers frequently abandon legitimate repair and replacement entitlements simply because tracking down physical documentation or navigating bureaucratic claims proves too exhausting or occurs long past forgotten statutory deadlines.

The primary target audience comprises Family Households managing dozens of concurrent appliances, consumer electronics, and valued equipment. Within this demographic, the core persona is the designated Household Manager—the family member tasked with logistical purchasing, equipment upkeep, and domestic organization. This individual requires an orderly, centralized repository to replace fragmented filing systems, overflowing junk drawers, and unindexed photo reels.

Covered AI delivers a streamlined digital vault that permanently eliminates physical receipt clutter. The platform pairs high-fidelity optical extraction with conversational artificial intelligence to synthesize dense terms into plain-language coverage summaries. Supported by automated, proactive expiration reminders, Covered AI guarantees that household managers preserve and exercise their consumer rights before manufacturer or statutory coverage windows expire.

## 2. User Need Validation

Primary user discovery confirmed that physical warranty management represents a significant friction point for modern homes. Across a discovery cohort of 30 surveyed participants, 21 individuals (70%) explicitly confirmed having experienced difficulty tracking down receipts or completely forfeiting valid warranty coverage due to an unnoticed expiration date.

Participants highlighted frustration with illegible thermal receipts, complex online registration portals, and the time commitment required to parse multi-page policy booklets. Furthermore, 87% of respondents reported a strong desire to eliminate paper accumulation altogether, indicating an immediate willingness to adopt a streamlined camera-driven workflow to digitize, verify, and monitor future retail purchases.

## 3. Success Metrics & Impact (KPIs)

Because household durable goods fail sporadically rather than continuously, platform performance cannot be measured purely by claim volume. Instead, metrics center on proactive asset tracking, vault health, and the realization of consumer entitlements during operational failures.

| Metric Area | Target Objective | Strategic Rationale |
|---|---|---|
| Vault Activation & Depth | 85% first-week logging; 5+ items per household within 30 days | Validates onboarding adoption and ensures comprehensive domestic asset indexing. |
| Resolution & Rights Fulfillment | 80%+ clear AI rulings with auto-generated claims for failures | Ensures users receive actionable assistance and eliminates manual claim friction. |
| Expiration Rescue Rate | 100% notification delivery; 0% accidental forfeitures | Measures proactive alert utility at 30-day and 7-day pre-expiry milestones. |

## 4. Minimum Viable Product (MVP) Scope

The semester release focuses strictly on the core path to user value, removing unnecessary administrative overhead while validating the ingestion, monitoring, and claim flows.

### Fast Ingestion & Verification
Users can rapidly digitize proof of purchase via physical camera capture or digital document upload (PDF/JPG). An optical extraction engine parses merchant details, purchase date, and product identifiers, instantly populating an editable verification card so users can confirm critical metadata in seconds.

### Proactive Expiration Alerts
The system continuously tracks active warranties against real-time system clocks. Proactive push alerts are queued and delivered at 30-day and 7-day intervals prior to expiration, ensuring that users have ample time to inspect equipment, address existing issues, and initiate service appointments.

### Warranty AI Assistant & Claim Drafting
A localized conversational agent ingests manufacturer warranty conditions to deliver clear, unambiguous coverage evaluations. When a defect falls within legal or commercial terms, the assistant automatically synthesizes an itemized customer service inquiry letter, ready to copy and send without requiring third-party mailbox integrations in Phase 1.

## 5. Business Considerations & Risk Management

### Competitive Landscape
Generic storage services, cloud drives, and basic notes applications allow users to retain receipt snapshots, yet they remain passive archives devoid of intelligence. Covered AI differentiates through automated policy extraction, proactive date tracking, and immediate policy interpretation, converting static receipts into actionable consumer protection.

### Monetization Strategy
Phase 1 provides unrestricted free access to maximize organic acquisition, refine machine learning extraction accuracy, and evaluate core engagement loops. Phase 2 introduces a tiered freemium model that caps free document storage at 12 active appliances, introducing an affordable premium subscription for larger inventories alongside contextual commercial partnerships with verified service networks and extended warranty underwriters.

### Legal Disclaimer & Compliance
Covered AI operates exclusively as an assistive organizational and informational instrument. The platform does not dispense formal legal counsel. A mandatory onboarding agreement requires users to acknowledge that claim letters and policy verdicts are synthesized drafts, and that direct communication, negotiations, and disputes with merchants and certified repair facilities remain the user's ultimate responsibility.

## 6. UI/UX Screen Specifications (Stitch Design Blueprint)

The interface adheres to a minimalist visual philosophy characterized by progressive disclosure, generous negative space, neutral palettes, and low cognitive load.

### Screen 0: Legal Terms & Onboarding Gate
A focused onboarding card presented on a neutral canvas. The layout details the informational nature of the service, potential optical scan discrepancies, and user responsibilities regarding vendor interactions. An explicit acknowledgment checkbox unlocks the primary access button, establishing compliance before granting access to the home interface.

### Screen 1: Home Dashboard (Minimalist Hub)
The central operational screen features a restrained top navigation bar with the brand logo, an unread notification bell, and a persistent conversational AI shortcut. Directly beneath, an alert banner surfaces equipment approaching expiration within 30 days. The core body comprises a tidy card feed of stored household items, each presenting only the product name, acquisition date, and a color-coded warranty status badge. Detailed purchase metadata remains suppressed until direct item interaction. A floating, centered action button facilitates immediate product registration.

### Screen 2: Ingestion Trigger Sheet
Initiated via the primary action button, this minimalist bottom sheet slides smoothly over the dashboard, presenting three distinct, unencumbered entry points: Capture Receipt (direct camera access), Upload Document/Image (system file picker supporting image and PDF formats), and Manual Form Entry (for items lacking documentation).

### Screen 3: Scan Preview & Data Verification
A split-screen confirmation view designed to streamline verification. The top half displays a zoomable image of the captured receipt, while the bottom section hosts concise, pre-filled editable inputs: Product Name, Brand/Manufacturer, Purchase Date, and Warranty Duration (in months). The view concludes with a prominent confirmation button saving the validated record directly into the vault.

### Screen 4: Product Master Detail View
Accessible by tapping any registered item on the dashboard. This view expands the asset into an exhaustive card displaying brand identity, model identifiers, serial numbers, purchase date, and exact remaining coverage time. An interactive thumbnail opens the original high-resolution receipt, accompanied by edit, archive, and delete tools. The visual focal point is a primary action card prompting the user to query the AI assistant regarding product defects or maintenance inquiries.

### Screen 5: Expiration Reminders Drawer
A clean modal drawer accessible from the dashboard notification icon. It categorizes assets crossing the 30-day and 7-day expiration thresholds. Each entry includes direct shortcuts to inspect the master detail sheet or immediately trigger an AI coverage diagnostic prior to lapse.

### Screen 6: Warranty AI Assistant & Customer Support Claim Drafter
A context-aware messaging interface populated with the active product metadata. The user describes the mechanical or electronic defect in conversational language. The AI parses policy terms and returns a definitive, plain-language coverage verdict. Immediately below the evaluation, the assistant renders an interactive action card containing a pre-composed, formal claim notice addressed to the merchant or importer, accompanied by a single-tap button to copy the drafted text to the system clipboard.

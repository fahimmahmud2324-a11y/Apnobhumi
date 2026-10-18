# ApnoBhumi (আপনভূমি)

A Bangla web app that helps ordinary buyers in Bangladesh through land purchase: a step-by-step guide, a rule-based document checker, and a mutation (namjari) tracker.

Built for the DIU LandTech Innovation Hackathon 2026, Land Tech Software track.

## The problem

Buying land involves two separate processes: deed registration (Ministry of Law) and mutation (Ministry of Land). Buyers face three specific problems:

1. A registered deed may not update the mutation record, so the buyer must start mutation separately, and many do not know this.
2. Buyers do not know which documents and details to check before buying, so mismatches (plot number, seller name, area) go unnoticed until a dispute.
3. After applying for mutation, buyers cannot easily tell when it has stalled or what to do about it.

## What it does

| Part | What it does |
|---|---|
| Step-by-step guide | Steps, responsible office and document checklist for buying, inheritance and gift. Makes mutation a clear separate step after registration. |
| Document checker | Compares deed and khatian details (mouza, plot number, seller name, area). Normalises units, fuzzy-matches Bangla names, and raises red flags for mismatches. |
| Verification list | Seven checks software cannot do (non-encumbrance certificate, litigation, possession, loans, khas or acquisition status, heirs' consent). The user records each result. |
| Mutation tracker | Counts down the 28-day target (working days or calendar days) and drafts a complaint letter when overdue. |

The report never says a purchase is "safe". It shows red flags and how many verifications are complete.

## Tech

- Single-file web app: HTML, CSS and vanilla JavaScript, fully in Bangla
- Light and dark themes, mobile friendly
- Data stays in the user's browser (localStorage). No server, no personal data leaves the device
- Rule-based logic: Levenshtein similarity for Bangla names, unit conversion, working-day date arithmetic
- Built-in self-test (7 tests) and demo cases in the "Demo and Self-test" tab

## Run it

Open `index.html` in any modern browser. No install needed. An internet connection is only used for Google Fonts, and the app falls back to system fonts offline.

## Limitations

- Data is entered by the user, not read from government portals, so wrong input gives a wrong report.
- The app cannot check litigation, earlier sales or possession itself. It lists them as tasks for the user.
- The checker's rules come from general knowledge and have not yet been reviewed by a lawyer.
- Whether the 28-day target counts working days or calendar days differs by source, so the user chooses. Public holidays are not counted.
- No login or server storage. Clearing browser data removes saved entries.
- This is an informational aid, not legal advice. Verify fees, deadlines and procedures on land.gov.bd and mutation.land.gov.bd.

## Planned next

Backend with login, Bangla OCR for deed and khatian photos, a payment-receipt vault, Bangla voice input, and integration with government APIs if available.

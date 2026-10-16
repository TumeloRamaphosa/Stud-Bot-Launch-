# gstack review — Stud-Bot launch kit (2026-10-16)

The review used gstack v1.55 **read-only** skills only (`/cso`, `/qa-only`, `/browse`, `/plan-eng-review`, `/health`). I applied their methods by hand. I did not run `/qa`, `/ship` or `/land-and-deploy`, and nothing was deployed.
No `rea-report.md` was available to include.

## /cso (security and compliance)
- **HIGH**: Real FNB business account number and branch were committed in `OFFER.md` and `automation/agentmail_send.json`. They also stay in git history, since the last commit only cleaned the README. **Fixed in the files.** The history still holds them, so consider rotating or treating them as public. No history rewrite was done.
- The only API reference is the env-var name `BLOTATO_API_KEY`, with no value. No IPs or secrets were found.
- POPIA: the README claims compliance, but there was no privacy notice, no Information Officer and no physical address. The email footer used "FNB Woodmead" in place of an address. **DRAFT Privacy and Terms pages added.**
- Unverified claims: "Halaal-certified" and the boxing-cup "partner brand" claim. **Removed.** The partner/BRICS relationship naming is also **removed**.

## /qa-only + /browse (landing page + live site)
- Unverified social proof: "57 signed. 43 slots left" and an attributed testimonial. This is a misleading-advertising risk under the Consumer Protection Act. **Landing page fixed** and the testimonial marked illustrative. The copy files still contain the counts (flagged below).
- "One warm intro per quarter, guaranteed" was an unconditional promise. **Softened.**
- Mobile: the header CTA could collide with the brand on narrow screens. There was no ≤420px breakpoint and tap targets were under 44px. **Fixed.**
- Accessibility: 12px muted text had low contrast, there was no focus style, no skip link and no `<main>` landmark, and the decorative "vs." was read out by screen readers. **Fixed.**
- **Live site** (https://studex-super-agents-site.vercel.app) is a React SPA. **Its source is NOT in this repo**, so these issues need a PR in the site repo:
  - Claims "Stitch payment gateway built in" and shows a "STITCH PAYMENTS" badge. This is false and must be removed.
  - Prices conflict: R1,599, R2,599, R4,999 and R1.5M/R2.5M/R5M tiers.
  - Mentions Kinyarwanda-first positioning (review it against the no-Rwanda-partners rule).
  - Contact is `t.ramaphosa@studex.dev`, while this kit uses `sales@studex-group.com`. Pick one.
  - The canonical/OG URLs point at www.studex-group.com.
  - No Privacy or Terms links were seen.

## /plan-eng-review
- Price was hard-coded in about 15 files. It is now one placeholder `{{STUDBOT_MONTHLY_PRICE}}`, to be filled once a price is confirmed (R2,599 / R3,500 / R4,599 under discussion). The founding vs regular split (old R3,250) also collapses to the same placeholder, so set it deliberately.
- The fulfilment margin table depends on the price. Recompute it when the price is set.
- Biltong shipping outside SA is unresolved, yet the copy promises "3 continents".

## /health
- This is a static content repo with no build, tests or linter. The JSON files are valid. Score: N/A (content-only).

## Still open (not changed)
- The "57 signed / 43 slots" counts remain in `copy/whatsapp-blast.md`, `copy/email-cold-outreach.md` and `automation/agentmail_send.json`. Verify them or remove them.
- Placeholders to fill: `{{PHYSICAL_ADDRESS}}`, Information Officer details, company reg no., VAT status, notice period, liability clause.

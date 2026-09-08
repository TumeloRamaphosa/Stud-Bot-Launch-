# Biltong Fulfillment — Ops Notes

## What we're promising

Every Stud-Bot subscriber receives **1kg Studex Wagyu biltong** shipped to their address, once per month, for as long as their R2,599/month subscription is active.

## Supply

- Source: Studex Meat inventory (studexmeat.com)
- SKU: 1kg Wagyu biltong (variant to lock: sliced vs whole, sliced default)
- Cost per unit at supply cost: estimate R450-700 (need to lock with fulfillment ops)
- Retail equivalent: R1,000-1,300

## Packaging

- Studex-branded parcel (obsidian black + gold, matches brand)
- Insert card: "You subscribed to Stud-Bot. Here's your monthly meat. — Studex"
- Insert card 2 (Month 1 only): welcome letter from Katjana + Global Markets Aspire tier onboarding link
- Insert card 3 (quarterly): "Your Global Markets intro slot is available. Reply to Katjana to activate."

## Shipping

- Courier: Aramex OR RAM (SA domestic, 2-3 day)
- Cost per parcel (SA nationwide): R150-200
- Cost per parcel (international, later phase): TBD, need international logistics partner
- Insurance: included for parcels > R500 declared value

## Timeline

- Signup + payment received → ops task auto-created in DenchClaw
- Day 1-3: agent deployment (in parallel with fulfillment)
- Day 3-5: first biltong parcel dispatched
- Every subsequent month: same day of month as signup (auto-scheduled)

## Ops workflow

1. CashClaw confirms payment received
2. CashClaw fires "biltong ship-out" task to Studex Meat fulfillment queue
3. Studex Meat packs + labels + hands to courier
4. Courier tracking number logged in DenchClaw against client record
5. Delivery confirmation triggers "Welcome" WhatsApp message to client via Hermes

## Unit economics

| Line | Cost |
|---|---|
| 1kg Wagyu biltong (supply) | R550 (mid-estimate) |
| Packaging + inserts | R60 |
| Courier + insurance | R175 |
| **Fulfillment cost/month/client** | **R785** |
| Stud-Bot agent inference (Qwen/DeepSeek via LiteLLM) | ~R150-300/month/client |
| Global Markets ops (founder time amortized) | R200/month/client |
| **Total variable cost/client/month** | **~R1,285** |
| **Revenue** | R2,599 |
| **Gross margin** | ~50% (R1,314/client/month) |

## First 50 clients: manual fulfillment

For first 50 clients, biltong ship-out is manual — Katjana coordinates with Studex Meat ops.

## After 50 clients: automate

- Auto-generate shipping labels via Shopify (studexmeat.com) admin API
- Auto-dispatch to fulfillment on payment confirmation
- Rate limit: max 20 parcels/day for first month, scale as ops permits

## Risk: supply

If Studex Meat can't fulfill 50+ Wagyu biltong parcels/month reliably in Month 1, either:
- (a) Cap founding-member cohort at Studex Meat's confirmed monthly capacity
- (b) Substitute with 500g Wagyu biltong + 500g other Studex Meat SKU (still under the "1kg meat" promise)

**Action:** Confirm Studex Meat monthly Wagyu biltong production capacity before publishing landing page. Contact: Studex Meat ops manager.

## International shipping (Phase 2)

- Nigeria, Egypt, UAE, Russia clients: too costly for monthly perishable
- Alternative: offer international clients a monthly R500 Studex credit toward a bulk shipment every quarter, OR a Studex Meat gift-drop when they travel to SA
- Do not promise monthly international biltong shipping in launch materials

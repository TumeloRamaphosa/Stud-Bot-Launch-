# Stud-Bot product plan

Stud-Bot is the Studex Super Agents subscription for South African small businesses: an agent that answers customers (in text and by voice), runs a few proven weekly workflows, and asks the owner before anything sends, posts or pays. The workflows follow the Claude for Small Business model: small, named jobs with an approval step, rather than an open-ended chatbot.

## Who it is for (round 1)

Restaurants, retail, salons and tutoring centres in Sandton, Cape Town, Durban and Pretoria. The owner still answers WhatsApp and does admin personally.

## What the client gets

| Part | What it does | Built on | In v1 |
|---|---|---|---|
| Customer agent | Answers enquiries on WhatsApp, email, Instagram and Facebook; remembers each customer | Hermes (WhatsApp), Studex Brain memory | Yes |
| Voice | Talks to customers by voice | Studex speaking agents (StudExClaw) | Yes, confirm channels before launch |
| Speed to lead | Replies to every new lead within minutes and logs it | `/speed-to-lead` pattern | Yes |
| Monday brief | One WhatsApp summary each Monday: enquiries, sales, open quotes, what needs the owner | `/monday-brief` pattern | Yes |
| Quotes and follow-ups | Drafts quotes from the client's price list; polite invoice reminders | `/proposal-builder`, invoice-chase pattern | v1.1 |
| Month-end | Month-end summary for the client's bookkeeper | `/close-month` pattern | v2 |
| Biltong | 1kg Studex Wagyu biltong monthly | studexmeat.com fulfilment | Yes (SA only) |
| Global Markets access | Warm introductions, subject to fit | Studex Global Markets | Yes |

## How a client is set up (48 hours)

1. **Hour 0:** signup, invoice from CashClaw, payment through the Shopify link.
2. **Day 1:** discovery call (20 min); connect WhatsApp Business and the client's price list; agent folder created from the client template.
3. **Day 2:** agent live on WhatsApp; first Monday brief scheduled; owner approves the first replies.
4. **Week 2:** check-in; add quotes and follow-ups.

Clients who need more than this get the 5-day FDE bootcamp (see the studex-fde repo) instead.

## Design rules for every page and message

- One price everywhere: `{{STUDBOT_MONTHLY_PRICE}}` until it is set.
- Only claims we can prove: no slot counts, certifications or partners unless verified and consented.
- Privacy and Terms linked from every page; POPIA details filled before launch.
- Approval is visible: every page says the owner approves anything that sends, posts or pays.
- Mobile first: most owners will open this from WhatsApp.

## Roadmap

| Version | Adds | Gate |
|---|---|---|
| v1 | Customer agent, voice, speed to lead, Monday brief | Price, POPIA details and slot counts resolved; first 10 clients |
| v1.1 | Quotes and follow-ups | 10 clients live for 2 weeks |
| v2 | Month-end, Instagram/Facebook DMs in one inbox | 50 clients |

## Open decisions (Tumelo)

1. Price: R2,599, R3,500 or R4,599, and whether there is a founding price.
2. POPIA: physical address, Information Officer, company registration and VAT status.
3. "57 signed / 43 slots" counts in the WhatsApp and email copy: real, or remove.
4. Which repo holds the live site (studex-super-agents-site.vercel.app), so it can be brought in line.
5. Voice: which channels at launch (WhatsApp voice notes, phone calls, or both).

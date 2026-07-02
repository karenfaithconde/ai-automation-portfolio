# Client Onboarding — Stripe + Airtable + Gmail

## What it does
Automatically captures a payment from Stripe, adds the client to an Airtable CRM, and sends them a welcome email — all within seconds of the payment going through. No manual data entry, no forgetting to follow up.

## Tools used
- Make.com
- Stripe (sandbox/test mode)
- Stripe CLI
- Airtable
- Gmail
- Make Webhook

## Real world use case
Elena runs a coaching program. Every time someone pays for a session, she used to manually add them to her client list and send a welcome email herself. If she was busy or forgot, new clients would sit around wondering if their payment even went through. This automation removes that gap completely — the moment a payment succeeds, the client is added to her CRM and gets a welcome email instantly.

## How it works
1. A client pays through Stripe
2. Stripe instantly sends a webhook to Make the moment the payment succeeds — no polling, no delay
3. Make creates a new record in Airtable with the client's name, email, amount paid, and the date they joined
4. Make sends the client a welcome email confirming their payment and spot in the program
5. Everything happens in seconds, with zero manual work

## What I learned
This project took me noticeably longer than the others — it was my first time working with a payment provider and I hit a lot of walls along the way. Here's what went wrong and how I fixed each one:

**Stripe CLI login kept timing out.** The normal `stripe login` command opens a browser to confirm, but it kept saying "exceeded max attempts" before I could click confirm. I fixed it by logging in directly with my API key instead: `stripe login --api-key sk_test_...`

**The customer's email came back empty.** Test payments from the CLI don't always include a receipt email, so my Gmail "To" field kept failing with a missing value error. I fixed this using Make's `ifempty()` function, which falls back to a default email if the real one is missing. In a real payment, Stripe always includes the customer's actual email, so this fallback would rarely even trigger.

**The Name field was blank.** I had mapped it to `Object: Customer`, but that's just an internal Stripe customer ID, not an actual name. I had to dig into the Stripe data structure to find the right field — `Object → Shipping → Name` — and remap it.

**The amount was wrong by 100x.** Stripe sends payment amounts in cents, not dollars. My Airtable was showing $2,000.00 for what was actually a $20 test payment. I had to manually add `/ 100` to the mapping to convert it correctly — and I made this same mistake twice, once in Airtable and again in the Gmail email body, before catching both.

Setting up a webhook-based integration with a real payment provider was a completely different experience from my earlier form-based projects. Debugging Stripe's data structure took patience, but understanding how payment data flows through an automation is a skill I know real clients will pay for.

## Files in this repo
- `blueprint.json` — Make.com automation file
- `canvas-screenshot.png` — all 3 modules connected in Make
- `airtable-screenshot.png` — Airtable CRM with a captured client record
- `email-screenshot.png` — welcome email sent automatically after payment

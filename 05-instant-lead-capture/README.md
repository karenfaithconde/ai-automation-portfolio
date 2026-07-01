# Instant Lead Capture (Webhook Version)

## What it does
Captures a lead the moment they submit a form — no waiting 
around. Their info gets saved to a spreadsheet and they get 
a confirmation email right away, automatically.

## Tools used
- Tally (form builder)
- Make.com
- Webhooks (instant trigger)
- Google Sheets
- Gmail
- Error handling (Retry)

## Real world use case
My first lead capture automation (Project 1) checked Google 
Forms every 15 minutes for new responses. That's fine for 
learning, but not good enough for a real business — a 
customer submitting a form shouldn't wait 15 minutes for 
confirmation. This version uses a webhook instead, so the 
moment someone submits the form, the automation fires 
instantly.

## How it works
1. Someone fills out the form and hits submit
2. That submission is instantly sent to Make — no delay
3. Their Name and Email get saved to Google Sheets right away
4. They immediately receive a confirmation email
5. If sending the email fails for any reason, Make 
   automatically tries again up to 3 times before giving up

Basically: submit form → get saved → get confirmed, all in 
seconds.

## What I learned
This project taught me the difference between "pull" and 
"push" automation. My earlier projects all pulled data on 
a schedule (checking every 15 minutes). Webhooks flip that 
around — the form pushes data to Make the instant it happens.

I also learned that Tally structures its data differently 
than Google Forms. Instead of a labeled `answers` object, 
it returns a `fields` array, so I had to map by array 
position (`fields[1]` for Name, `fields[2]` for Email) 
instead of clicking a labeled dropdown.

Honestly, Tally was easier to work with than Google Forms. 
With Google Forms I kept running into glitches where the 
mapping just wouldn't work — I'd map Name and Email 
correctly, submit a test response, and nothing would show 
up in Google Sheets. I spent a lot of time troubleshooting 
thinking I had done something wrong, when it turned out to 
just be Make glitching. Closing and reopening the scenario 
usually fixed it. Tally didn't give me any of these issues.

Lastly, I got confused with error handlers at first. I kept 
selecting Retry and getting an error saying "Store 
incomplete executions" was required, with no clear next 
step shown. It turned out the fix was simple — I just had 
to turn that setting on in the scenario settings. Once I 
found it, everything worked.

## Files in this repo
- `blueprint.json` — Make.com automation file
- `canvas-screenshot.png` — full scenario with webhook, 
  sheets, gmail, and retry handler
- `sheet-screenshot.png` — Google Sheet with captured lead
- `email-screenshot.png` — confirmation email received
- `tally-webhook-screenshot.png` — Tally form connected 
  to the Make webhook

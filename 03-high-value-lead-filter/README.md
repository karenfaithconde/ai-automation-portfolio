# High Value Lead Filter

## What it does
Automatically captures project inquiries, saves all leads 
to Google Sheets, and routes them based on budget — high 
value leads trigger a priority alert to the business owner, 
low value leads receive a polite acknowledgement email.

## Tools used
- Make.com
- Google Forms
- Google Sheets
- Gmail
- Make Router

## Real world use case
A freelance web designer named Marco receives project 
inquiries through a contact form. Before this automation, 
he had to manually check every submission and decide how 
to respond. Now the automation checks the budget and sends 
the right response automatically — Marco never misses a 
high value lead again.

## How it works
1. Client submits a project inquiry form
2. Make saves the lead to Google Sheets immediately
3. Router checks the budget amount
4. Budget PHP 10,000 and above → Marco receives a 
   hot lead alert email with the client's full details
5. Budget below PHP 10,000 → Client receives a polite 
   acknowledgement email

## What I learned
This was my first time using a Router in Make. I learned 
that a Filter stops the automation completely if a condition 
is not met, while a Router splits the automation into 
multiple paths so every lead still gets handled — just 
differently based on the condition.

I also learned that Make needs at least one test submission 
before it can detect form fields for mapping. Without that 
test response the dropdowns stay empty.

This project felt the most realistic so far. A real 
freelancer could use this exact automation today.

## Files in this repo
- `lead-filter-blueprint.json` — Make.com automation file
- `lead-filter-canvas.png` — full scenario with router and both paths
- `leads-sheet.png` — Google Sheet with all captured leads
- `hot-lead-alert.png` — priority alert email for high value leads
- `low-lead-reply.png` — acknowledgement email for low value leads

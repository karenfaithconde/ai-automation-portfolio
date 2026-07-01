# AI Lead Qualifier

## What it does
Captures project inquiries, saves them to Google Sheets, 
and uses AI to read the description and decide if it's a 
good fit. Web design leads get a priority alert to the 
owner. Everything else gets a polite rejection — automatically.

## Tools used
- Make.com
- Google Forms
- Google Sheets
- Groq AI (llama-3.3-70b-versatile)
- Gmail
- Make Router

## Real world use case
Marco is a freelance web designer. Every week he gets 
inquiries from people who need logo design, video editing, 
social media — things he doesn't do. He was spending time 
reading through every single message just to find out it 
wasn't relevant. This automation fixes that. The AI reads 
each inquiry and handles the routing automatically. Marco 
only gets notified when it's actually worth his time.

## How it works
1. Client submits the inquiry form with their name, email, 
   budget, and project description
2. Make saves the entry to Google Sheets right away
3. The project description gets sent to Groq AI, which 
   replies with either WEB DESIGN or NOT RELEVANT
4. A Router reads the AI reply and takes action:
   - WEB DESIGN → Marco gets a full lead alert by email
   - NOT RELEVANT → Client gets a polite email explaining 
     the agency only does web design
5. The whole thing runs in seconds with no human involved

## What I learned
Coming back to this after a few days away, I took time to 
review my previous work and rebuild my understanding step 
by step before continuing. It reminded me how important 
it is to document as you go — good notes save a lot of 
time later.

This was also my first time connecting an AI API to an 
automation. The difference from my earlier projects is that 
the AI isn't just moving data — it's actually reading the 
content and making a decision. That was a big shift for me.

I originally planned to use Gemini AI but kept hitting 
quota limits even on fresh accounts. After some research 
I figured out the free tier is likely restricted by IP 
address, so switching accounts from the same network 
didn't help. I switched to Groq instead — it's free, 
fast, and runs on custom LPU chips that make it quicker 
than most alternatives. It worked on the first try.

One thing I'll never forget from this project — always 
remove API keys before pushing to GitHub. I almost 
uploaded mine by accident. GitHub caught it and blocked 
the commit, which was a good reminder that API keys are 
private credentials and exposing them is a real security 
risk. The blueprint in this repo has the key replaced 
with a placeholder.

Everything I'm building here is self-taught — through 
documentation, hands-on practice, and a lot of 
problem solving. Every error I hit teaches me something 
new.

## Files in this repo
- `blueprint.json` — Make.com automation file 
  (API key removed — replace with your own Groq key)
- `canvas-screenshot.png` — full scenario with all modules
- `sheet-screenshot.png` — Google Sheet with captured leads
- `web-design-email.png` — priority alert for web design leads
- `not-relevant-email.png` — rejection email for irrelevant leads

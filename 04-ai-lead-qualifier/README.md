# AI Lead Qualifier

## What it does
Automatically captures project inquiries, saves them to 
Google Sheets, and uses AI to read the project description 
and decide if it is a good fit — web design leads get a 
priority alert sent to the business owner, irrelevant leads 
get a polite rejection email automatically.

## Tools used
- Make.com
- Google Forms
- Google Sheets
- Groq AI (llama-3.3-70b-versatile)
- Gmail
- Make Router

## Real world use case
A freelance web designer named Marco receives dozens of 
project inquiries every week. Many of them are for services 
he does not offer — like logo design, video editing, or 
social media management. Before this automation, Marco had 
to manually read every single submission just to find out 
it was not relevant. Now the AI does that job for him 
automatically.

## How it works
Think of this automation as a smart assistant that reads 
every inquiry and decides what to do with it.

1. A client fills out the Project Inquiry Form with their 
   name, email, budget, and project description
2. Make immediately saves their information to Google Sheets 
   so nothing gets lost
3. The project description is sent to Groq AI — an AI that 
   reads it and replies with either WEB DESIGN or NOT RELEVANT
4. A Router checks what the AI said and splits into two paths:
   - If the AI said WEB DESIGN → Marco receives a hot lead 
     alert email with the client's full details so he can 
     follow up immediately
   - If the AI said NOT RELEVANT → The client automatically 
     receives a polite email explaining that the agency only 
     handles web design projects
5. Everything happens in seconds — no human needed

## What I learned
My last project was 4 days ago so when I came back to this 
one, I had forgotten most of what I did. It took me about 
2 hours just to remember how everything worked again. I had 
to Google things and ask AI to explain each step one by one 
before it clicked again.

That taught me something important — documenting my work 
properly matters. The better your notes, the faster you 
can pick up where you left off.

I also learned how to connect an AI API inside an automation 
for the first time. Instead of just moving data around, the 
AI actually reads the content and makes a decision. That 
felt like a big step up from the previous projects.

Originally I was supposed to use Gemini AI for this project 
since that was what my learning roadmap recommended. I got 
my API key from Google AI Studio and set everything up — 
but every time I tested it, Gemini kept returning a quota 
exceeded error even though I had just created the account. 
I tried creating multiple Google accounts and generating 
new API keys but the same error kept appearing. I later 
found out that Gemini's free tier quota is likely tied to 
the IP address, meaning all accounts from the same network 
share the same limit. So switching accounts did not help.

I asked Claude for a free alternative and it recommended 
Groq. Groq is a free AI API platform that is actually 
faster than Gemini and OpenAI for most tasks because it 
runs on custom hardware chips called LPUs. It has a 
generous free tier, does not require a credit card, and 
works perfectly for automation workflows. I also considered 
using the Claude API but it requires billing which I cannot 
afford right now.

I replaced Gemini with Groq and it worked on the first try.

One mistake I almost made was uploading my Groq API key 
to GitHub. GitHub actually detected it and blocked the 
upload — which was a good warning. API keys are private 
credentials and exposing them is a security risk. I removed 
the key from the file and replaced it with a placeholder 
before uploading. I will never forget that again.

I am learning all of this for free — no paid courses, no 
coach, just documentation, AI tools, and a lot of trial 
and error. It is harder this way but every problem I solve 
teaches me more than any tutorial would.

## Files in this repo
- `blueprint.json` — Make.com automation file 
  (API key removed for security — replace with your own)
- `canvas-screenshot.png` — full scenario with all modules
- `sheet-screenshot.png` — Google Sheet with captured leads
- `web-design-email.png` — priority alert for web design leads
- `not-relevant-email.png` — rejection email for irrelevant leads

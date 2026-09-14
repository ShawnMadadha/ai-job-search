---
framework_version: 1.0.0
---

# Interview Preparation Guide

<!-- SETUP: STAR examples are personalized by running /setup based on your actual experience -->

## STAR Format

Structure answers as: **Situation** (context), **Task** (your responsibility), **Action** (what you did), **Result** (outcome).

Keep answers to 1-2 minutes. Be specific. End with what you learned or would do differently.

## Ready-Made STAR Examples

<!-- Populated by /setup from Shawn's actual CV. Every S/T/A/R below traces to a real
project or role in 01-candidate-profile.md. Sharpen the wording in your own voice before an
interview, but do not add facts that are not in the profile. -->

### 1. Bowser (Working under extreme time pressure / systems integration)
**S:** At HackUSF 2026 my team set out to build an autonomous therapy robot for pediatric rehabilitation, integrating hardware, computer vision, and multi-agent AI. We had 36 hours and no working prototype of any piece.
**T:** I was responsible for the clinical application design and co-built the hardware, which meant I owned both the thing the therapist would touch and the Roomba it had to drive.
**A:** I scoped hard to what could actually demo: ESP32 talking to a Roomba 690 over the Open Interface serial protocol, real-time pose tracking for the gamified exercises, and four Google ADK agents split by responsibility so we could build and test them in parallel rather than as one monolith. One agent handled live audio input, one did hospital database lookups, and the navigation path used OpenCV, MediaPipe, YOLO, and depth estimation. When an integration failed we cut the feature rather than debug past our deadline.
**R:** We demoed a working autonomous robot running gamified rehabilitation exercises and won the hackathon. The agent-per-responsibility split is the decision I would make again, because it was what let four people work at once instead of queueing behind one integration.
**Use for:** "Tell me about a time you worked under a tight deadline", "Describe a technically complex project", "How do you decide what to cut?"

### 2. Tarmac (Leading peers / delegation)
**S:** Over three months in early 2026 I led a team of four developers building an iOS travel app with AI agents for flight delay explanation, city recommendations, and expense parsing.
**T:** I was the lead, which meant architecting the backend API and also making four people's work add up to one shippable app. None of them reported to me, so I had no authority beyond whatever credibility I earned.
**A:** I architected the Python/FastAPI backend first so there was a contract everyone could build against, then ran weekly sprints with explicit task delegation and did code reviews on every pull request. I kept the interfaces between the SwiftUI front end and the agent services narrow on purpose, so two people could work without blocking each other.
**R:** We shipped the app with all three AI features working. The lesson that stuck was that defining the API contract before assigning any work was what prevented most coordination problems, rather than any amount of meeting about them afterward.
**Use for:** "Tell me about a time you led a team", "How do you handle disagreement?", "Describe a time you had influence without authority"

### 3. Orlando Health (Operational discipline / automation in a regulated environment)
**S:** I joined Orlando Health on contract as a Technology Specialist covering network infrastructure across three hospital campuses, serving over 2,000 medical staff where downtime has patient consequences.
**T:** I was accountable for uptime and for resolving support tickets inside SLA windows, in an environment where I had to follow established process rather than invent my own.
**A:** I administered and monitored the infrastructure through Active Directory and remote management tools, and worked tickets to SLA. Rather than absorb the repetitive load, I wrote Python and PowerShell scripts to automate routine maintenance tasks I was doing by hand.
**R:** I held 99.9% uptime, resolved over 50 tickets within their SLA windows, and the automation removed about 15 hours of manual work per week that the team kept using after my contract ended. It was also the clearest lesson I have had in working inside someone else's process instead of my own.
**Use for:** "Tell me about a time you improved a process", "How do you handle repetitive work?", "Describe working in a highly regulated or high-stakes environment", "Give an example of following an established process"

### 4. Chronos (formerly Geodo) (Architecture ownership at scale)
**S:** As Co-Founder and CTO of Chronos (formerly Geodo), from May to August 2026, I was responsible for an AI-native GTM platform that acts as a digital twin for B2B sales teams, which has grown to over 3,000 companies, 350M+ enriched leads, and $20B+ in managed pipeline.
**T:** I own the core technical architecture and performance monitoring end to end. There is nobody above me to escalate an architecture decision to.
**A:** I built the product on Next.js 15, TypeScript, and Tailwind v4 over a pnpm monorepo, with Drizzle on Aurora Serverless v2 Postgres. For the enrichment and outbound workloads I used SQS and Lambda event pipelines with dead-letter queues so a single bad record could not stall a queue, and SSE row streaming so the UI could render results as they arrived instead of waiting on a full response. Infrastructure is AWS CDK, and I instrumented the whole thing with OpenTelemetry so I could see where time actually went rather than guess. I use Claude Code as my daily development environment across the monorepo.
**R:** The platform handles that lead volume and pipeline in production, and the observability work is what lets me find performance problems before users report them. The decision I would defend hardest is putting dead-letter queues and tracing in early, because both felt premature at the time and both paid for themselves.
**Use for:** "Tell me about a system you designed", "How do you debug a performance problem?", "What's a technical decision you're proud of?", "How do you handle failure in a distributed system?"

### 5. Onyx Aura (Safety-critical judgment)
**S:** We built an autonomous voice AI that handles live pharmacy calls, streaming ElevenLabs Multilingual v3 from Gemini 2.0 over Twilio WebSockets. The obvious risk was an agent confidently confirming a prescription that would hurt someone.
**T:** I engineered and validated the safety pipeline, meaning I owned the part whose failure mode was the serious one.
**A:** I built a real-time check that cross-referenced the prescription being discussed against the patient's allergy profile using Gemini 2.0 Flash, and gave it the authority to halt a dangerous medication mid-conversation rather than flag it afterward. I then validated it against cases designed to make it fail, because a safety check that has only been tested on the happy path is not a safety check.
**R:** The system ran live calls at sub-second response times while autonomously stopping dangerous medications mid-conversation. My takeaway is that in an agent system the interesting engineering is in what the agent is allowed to do when it is uncertain, not in what it does when it is right.
**Use for:** "Tell me about a time you considered risk or safety", "How do you test AI systems?", "Describe a time you pushed back on a design", "What does responsible AI mean in practice to you?"

<!-- Add more STAR examples as needed. Aim for 4-6 covering different competencies. -->

## Common Tough Questions

### "Why did you leave [previous company]?" / "Walk me through your timeline."
> Shawn has not been fired or pushed out of anything, so the honest framing is transitions, not
> departures. Orlando Health was a fixed-term contract that ran October to December 2025 and
> ended on schedule. R3 Vacations and Triune Tek both wound down in May 2026 because Chronos (formerly Geodo) became
> a full-time commitment and running three things at once was no longer honest work. Say that
> plainly and move forward. Do not volunteer that anything ended badly, because nothing did.

### "You're a CTO. Why are you applying for an internship?"
> The question that will come up most, so have a real answer. The truthful one: almost everything
> he has built, he has built as the most senior technical person in the room, and that has a
> ceiling. He has never had his code reviewed by an engineer more experienced than himself, never
> worked in a codebase he did not largely write, and never seen how a mature organization does
> release engineering or testing discipline. That is the specific gap he wants closed, and it is
> not something founding solo can teach. Pair it with what he brings in exchange: someone who has
> already run production systems and will not need hand-holding on fundamentals.

### "How will you balance this with being CTO of Chronos (formerly Geodo)?"
> Do not be vague here, it reads as evasive. Be concrete about hours and term. Summer is a
> full-time internship window. School-year work is part-time or contract only, around a full UF
> course load. He has run concurrent commitments for years, including three ventures at once
> while carrying a 3.8 GPA, so the track record supports the claim. Offer the specifics before
> being pressed for them.

### "You don't have [specific skill/experience]."
> Name the gap without flinching, then bridge to the nearest real thing, then show the learning
> pattern. The pattern is the strongest part of the answer: he learned Aurora Serverless v2,
> SQS/Lambda with DLQs, AWS CDK, and OpenTelemetry because Chronos (formerly Geodo) needed them in production, not
> from a course. Worked examples:
> - **No Kubernetes:** he has run serverless and event-driven infrastructure on AWS at scale, and
>   understands the problems orchestration solves even though he has solved them with Lambda, SQS,
>   and CDK instead. He has not run a cluster.
> - **No Go or Rust:** he is fluent in Python and TypeScript and has shipped in C, C++, C#, Java,
>   and Swift, so a new language is a matter of weeks, not a career change.
> - **No ML model training:** be honest. His AI work is applied agent engineering on top of
>   foundation models, not training or research. He should not imply otherwise.
> - **No large-team experience:** true, and it is the reason he is applying. Do not treat it as a
>   weakness to deflect.

### "Where do you see yourself in 5 years?"
> Five years puts him around 2031, three years past graduating in May 2028. Honest and aligned:
> a senior engineer with real architectural ownership of AI systems that take action in the
> world, whether that is inside a company whose scale he could not reach alone or at Chronos if it
> grows into that. What he wants to be true by then is that he has learned to build with other
> engineers rather than around them. Avoid "running my own company" as the whole answer, since it
> invites the interviewer to read the role as a layover.

### "What's your biggest weakness?"
> Use a real one with a real mitigation. Best option: having owned everything himself for nine
> years, his instinct is to expand scope and fix whatever he notices, which is an asset in a
> founder and a liability on a team where that surface belongs to someone else. Mitigation he can
> point to: on Tarmac he defined the API contract up front precisely so that boundaries were
> explicit, and he now asks about scope boundaries at the start of a task rather than discovering
> them by crossing one. Second option: he optimizes for shipping, which has occasionally meant
> cutting a feature rather than debugging it, and he is learning when that tradeoff is wrong.
> Avoid "perfectionism" and "I work too hard", which read as non-answers.

### "Why this company specifically?"
> Customize per company. Must reference: specific projects, company values, market position, or team structure. Never give a generic answer.

## Questions You Should Ask Interviewers

### About the Role
- "What does a typical week look like in this role?"
- "What would success look like in the first 6 months?"
- "What's the biggest challenge the team is facing right now?"

### About the Team
- "How big is the team, and how do you divide work?"
- "What does the development/project lifecycle look like, from idea to production?"
- "How do you onboard new team members?"

### About Tech & Growth
- "What's your current tech stack for [relevant area]?"
- "Is there room to grow into more architectural or strategic decisions?"
- "How does the team stay current with new tools and methods?"

### About Culture (use these to prevent disappointment)
- "How would you describe the team culture?"
- "What does professional development look like here?"
- "Is there flexibility for remote/hybrid work?"
- "What's the balance between development/new projects and maintenance work?"
- "How would you describe the leadership style in this team?"
- "What do people who thrive here have in common?"

## Phone/Video Interview Tips
- Have STAR examples written out (use this file)
- Keep a glass of water nearby
- Smile when speaking (it changes your tone)
- Ask for clarification if a question is vague
- It's OK to take 5 seconds to think before answering
- End with: "Is there anything else you'd like to know about my background?"

## After the Application (Best Practice)

### Follow-Up Etiquette
- **Don't call to "stand out"** or to learn more about the role post-submission - this risks a negative impression
- If the employer specified a timeline, respect it and wait
- If no timeline was given and significant time has passed (2+ weeks), a brief call to ask about status is acceptable
- If you have genuinely new, relevant information to share, a short follow-up is fine

### Thank-You Notes
- When you receive any update (interview invitation, rejection, or status update), send a brief thank-you message
- Express appreciation for their time and the process
- Keep it short (2-3 sentences)

## Roleplay Guidelines
When the user asks for interview practice:
1. Ask which role/company to simulate
2. Start with easy warm-up questions ("Tell me about yourself")
3. Progress to role-specific technical questions
4. Include 1-2 behavioral questions using the competencies from the job posting
5. End with a tough question or curveball
6. After each answer, give brief feedback: what worked, what to sharpen
7. Suggest which STAR example would work best for each question

---
framework_version: 1.1.1
---

# Candidate Profile

## Identity
- **Name:** Shawn Madadha
- **Location:** Splits time between Inlet Beach, Florida and the San Francisco Bay Area (both accurate; LinkedIn lists the Bay Area). Mailing address: 170 River Rise Way, Inlet Beach, FL 32461
- **Phone:** (205) 981-3910
- **Email:** shawn4speed@gmail.com
- **LinkedIn:** https://linkedin.com/in/shawnmadadha
- **GitHub:** https://github.com/ShawnMadadha
- **Status:** Computer Science undergraduate at the University of Florida, **attending REMOTELY** (BS expected May 2028). Remote enrollment means full-time roles are compatible with his degree. Co-Founder & CTO of Chronos (formerly Geodo) from May to August 2026. Chronos ended in August 2026. Available now, seeking a role for Fall 2026 and beyond - internship, contract, or full-time. Looking for Summer 2027 internships, plus remote part-time, contract, or Fall 2026 work now.
- **Constraints:** Remote-first by preference. **Bay Area on-site and hybrid are viable year-round** - he is there regularly, so do not treat SF/Peninsula/South Bay as relocation-only. Florida panhandle on-site also works (Panama City ~30 min, Destin/Fort Walton Beach ~45 min). Gainesville is ~5h from Inlet Beach and not commutable. Other US metros are summer-relocation only. Must work around a full university course load during fall and spring terms.

### Languages

| Language | Level | Notes |
|----------|-------|-------|
| English | Native | Sole working language. A posting that requires any other language as a job condition is excluded by the Language Gate. |

## Education

| Degree | Period | Institution | Key Topics |
|--------|--------|-------------|------------|
| BS, Computer Science (GPA 3.8/4.0, expected May 2028) | 2026-2028 | University of Florida, Gainesville, FL | Computer science core curriculum |
| Associate of Arts (GPA 3.8/4.0) | 2023-2025 | Northwest Florida State College, Niceville, FL | General education transfer track; President's List; Phi Theta Kappa |

## Professional Experience

### Co-Founder & Chief Technology Officer - Chronos, formerly Geodo (May 2026 - Aug 2026)
Remote
- Co-founded and led all engineering for an AI-native GTM platform that acts as a digital twin for B2B sales teams, automating outbound, surfacing high-intent buyers, and managing pipeline through natural-language commands
- Grew the platform to 3,000+ companies, 350M+ enriched leads, and $20B+ in managed pipeline; owned core technical architecture and performance monitoring end to end
- Built and monitored on Next.js 15, TypeScript, and Tailwind v4 with a pnpm monorepo backend running Drizzle over Aurora Serverless v2 Postgres, SQS/Lambda event pipelines with DLQs, SSE row streaming, and AWS CDK with OpenTelemetry for infrastructure and observability
- Owned the programmatic email delivery layer end to end on a third-party agent-inbox provider API: per-account inbox provisioning, domain warm-up and placement, send-rate ramps tied to inbox age, and per-account daily caps
- Diagnosed a class of silent send failures where the provider rejected messages and the response was discarded, leaving contacts retried indefinitely; also rebuilt bounce recording and auto-suppression so undeliverable addresses stopped being sent to
- Hit the provider's inbox capacity ceiling in production and built multi-key pooling plus a fallback path to user-owned Gmail and Outlook inboxes so onboarding never blocked on provider capacity

### Technology Specialist (Contract) - Orlando Health (Oct 2025 - Dec 2025)
Orlando, FL
- Administered and monitored network infrastructure across 3 hospital campuses using Active Directory and remote management tools, troubleshooting issues and maintaining 99.9% uptime for systems serving 2,000+ medical staff
- Automated routine maintenance with Python and PowerShell scripts, reducing manual workload by 15 hrs/week
- Resolved 50+ support tickets within SLA windows

### Co-Founder - R3 Vacations (Sep 2023 - May 2026)
Florida
- Co-founded a short-term rental business operating 3 properties; built the company website and Airbnb listing pages, generating $225K+ in gross booking revenue over 3 years
- Owned P&L, dynamic pricing, guest operations, and vendor management, applying data analysis to drive year-over-year growth across the portfolio

### Founder - Triune Tek, LLC (Aug 2017 - May 2026)
Florida
- Founded a web and AI automation studio at 14; delivered custom sites and lead-gen for small-business clients end to end with a 100% on-time delivery rate
- Ran the full commercial cycle solo, including business analysis, sourcing, scoping, building, and client retention
- Improved average client page load speed by 40% through diagnostic audits and refactoring

## Independent Projects
- **Bowser** (Mar 2026): Autonomous Roomba 690 therapy robot for gamified pediatric rehabilitation. Designed the clinical application and co-built the hardware using ESP32 and Roomba OI serial, enabling real-time pose tracking. Integrated four Google ADK agents to orchestrate live audio input, hospital database lookups, and autonomous navigation using OpenCV, MediaPipe, YOLO, and depth estimation in a 36-hour sprint. Won HackUSF 2026.
- **Onyx Aura** (Mar 2026): Autonomous voice AI for live pharmacy calls. Co-developed using Twilio WebSockets and ElevenLabs Multilingual v3 streaming from Gemini 2.0, achieving sub-second response times. Engineered and validated a real-time safety pipeline that cross-referenced prescriptions against allergy profiles with Gemini 2.0 Flash, autonomously halting dangerous medications mid-conversation.
- **Materiality Watch** (May 2026), open source: AI-powered website change monitoring that inverts the usual model. The user describes in plain English what counts as a material change, and Claude evaluates every diff against those criteria, suppressing footer edits, ad rotation and copy polish. Portfolio mode across 1-50 URLs per run with a consolidated digest and per-URL timeline. Python. github.com/ShawnMadadha/materiality-watch
- **Kickoff** (Jun 2026), 8th of 45 teams at the Miami Cursor Hackathon: match-day companion for the FIFA World Cup 26 in Miami, routing fans to the right entrance at Hard Rock Stadium in their own language and surfacing nearby watch parties. Next.js 16, React 19, TypeScript, Tailwind v4, Leaflet, on Vercel. Live at kickoff-brown-tau.vercel.app
- **Open-source MCP contribution** (May 2026): contributed production-hardening features to `trypeggy/instagram_dm_mcp`, an open-source Model Context Protocol server. Added per-tool rate limiting to stay inside platform anti-abuse limits, and account-agnostic session handling so sessions persist per user rather than globally. NOTE: this is a contribution to someone else's repository, not his own MCP server. Describe it as a contribution and never as authorship.
- **Tarmac** (Jan 2026 - Mar 2026): iOS travel app built in SwiftUI with a Python/FastAPI backend and AI agents for delay explanation, city recommendations, and expense parsing. Led 4 developers, architected the backend API, and managed weekly sprints, code reviews, and task delegation.

## Technical Skills

### Programming & ML
- **Python** (advanced): FastAPI, LangChain, OpenCV, MediaPipe, YOLO, automation scripting
- **TypeScript / JavaScript** (advanced): Next.js 15, React, TanStack Query, Zod, Drizzle, Vitest, Tailwind v4, pnpm monorepos
- **SQL** (proficient): Postgres on Aurora Serverless v2, Drizzle ORM, database design
- **Swift** (working): SwiftUI iOS development
- **C, C++, C#, Java** (coursework and project level)
- **PowerShell** (working): Windows administration and maintenance automation
- **AI/agent engineering:** Gemini 2.0 and Gemini 2.0 Flash, Google ADK multi-agent orchestration, LangChain, ElevenLabs Multilingual v3 streaming
- **Agentic coding:** Claude Code for day-to-day development across the Chronos (formerly Geodo) monorepo

### Domain Expertise
- AI-native B2B GTM platforms and sales engineering
- Multi-agent orchestration and real-time voice AI pipelines
- Computer vision and pose tracking (OpenCV, MediaPipe, YOLO, depth estimation)
- Distributed event-driven backends (SQS/Lambda with DLQs, SSE streaming)
- Cloud infrastructure as code and production observability (AWS CDK, OpenTelemetry)
- Enterprise IT operations in a regulated healthcare environment (Active Directory, SLA-bound support)

### Software & Tools
AWS (Aurora Serverless v2, Lambda, SQS, CDK, Secrets Manager), OpenTelemetry, Google Cloud, Firebase, Twilio, ESP32, Active Directory, SAP S/4HANA, Git/GitHub, Claude Code, Microsoft Office Suite, Microsoft Outlook

## Publications
None.

## Awards
- **2x Hackathon Winner** - HackUSF 2026 and SASEHacks 2026
- **8th of 45 teams** - Miami Cursor Hackathon (2026)
- **4th of 20 teams** - NSEC Florida Regional Sales Engineering Competition (2026)
- **President's List** - Northwest Florida State College
- **Phi Theta Kappa Honor Society** - Northwest Florida State College

## References
<!-- Not yet collected. Candidates: the Orlando Health supervisor from the Oct-Dec 2025
contract, the Chronos (formerly Geodo) co-founder, and a Triune Tek client. Add name, title, company, email,
and phone before listing any referee on an application. -->

Available upon request.

# Search Queries for Job Scraper

Configured for **Shawn Madadha** - US market, remote-first, based in Inlet Beach, Florida.
Target: **immediate Fall 2026 starts** (full-time, contract, or part-time) as the priority, plus
**Summer 2027 internships** while that cycle is at peak season.

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

**Enabled for this profile:** `linkedin-search`, `freehire-search` (both country-agnostic).
**Disabled deliberately:** `jobindex-search`, `jobbank-search`, `jobdanmark-search`, `jobnet-search` - these are Denmark-only demos and cost nothing while disabled. Leave them off unless the target market changes.

**freehire-search scoping (required).** freehire crawls whole company career pages, so an unscoped query returns sales, clinical and operations postings alongside engineering. Always pass the US region and a category facet: `--region us --category backend,fullstack,ml_ai,devops`, adding `--remote remote` when remote-only is wanted, and prefer a role-shaped `-q` ("founding engineer", "AI engineer") over a bare word like "intern". Evidence: a 2026-09-13 run using `-q "intern" --region us` with no category returned two nursing postings and six sales roles inside 25 results. Use `--no-description` for the discovery pass, then `detail <slug>` on the shortlist.

The `site:` query templates in this file are the **WebSearch fallback** - for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** English only. Shawn's CLAUDE.md Languages table lists English (Native) and nothing else, so every query below is written in English and no translated variants are needed. A posting that requires any other language **as a job condition** is excluded before scoring by `04-job-evaluation.md`'s Language Gate, which is the single source of truth for that rule.

## Timing note

Summer internship recruiting in US tech runs far ahead of the work. Summer 2027 postings typically open between roughly August 2026 and January 2027, with the largest employers closing early and many using rolling review. Treat the current window as peak season and prioritize Priority 1 and 2 accordingly. Off-cycle and smaller companies post later, through spring 2027.

That cycle is real but it is not the whole search. Chronos ended in August 2026 and Shawn attends UF
remotely, so he is **available now** and a full-time role does not conflict with the degree. Immediate-start
work (Priority 0) is the top tier; Summer 2027 internships run alongside it, not ahead of it.

## Search Sites

Primary (US general and student-focused boards):
- **linkedin.com/jobs** - largest general board; also covered by the `linkedin-search` CLI
- **indeed.com** - largest US aggregator, strong for part-time and contract
- **joinhandshake.com** - university-network board; strongest single source for internships, and Shawn has University of Florida access
- **glassdoor.com** - general board plus company reviews for the behavioral red-flag research in `04-job-evaluation.md`
- **builtin.com** - startup and tech-company roles by metro, good remote coverage
- **wellfound.com** - early-stage startup roles; best match for the founding-engineer-shaped work Shawn is strongest at
- **dice.com** - IT, infrastructure, and contract-heavy listings (Priority 3)
- **simplify.jobs** and the community **Summer 2027 internship** GitHub lists - curated new-grad and internship trackers
- **ziprecruiter.com** - broad coverage, useful for part-time during the school year

Secondary (company career pages via Google):
- Direct `site:` searches against target companies listed in CLAUDE.md's Target Sectors
- ATS domains are often where the real posting lives: `site:boards.greenhouse.io`, `site:jobs.lever.co`, `site:job-boards.greenhouse.io`, `site:ashbyhq.com`, `site:myworkdayjobs.com`

## Query Categories

Queries are grouped by priority. All are written in English (see Language scope above). Combine with `remote` as the default location term; add a specific metro only for the summer-relocation case.

**Organize by function, not job title.** The same work carries different titles across companies (a "Software Engineer Intern" at one employer is a "Technical Intern", "Engineering Intern", or "SWE Co-op" at another). Each category below names the function and lists several title variants rather than betting a tier on one exact string.

### Priority 0: Immediate-start full-time / contract (Fall 2026)

**Top priority.** Available now, no graduation gate - remote UF enrollment means a full-time role and the
degree coexist. Early-stage founding-engineer work is the closest match to how he actually operates: sole
ownership of architecture through production observability, 0-to-1 ambiguity, direct user access. Screen
these against the Deal-breakers in CLAUDE.md - equity-only and commission-only roles are excluded.

```
site:wellfound.com "founding engineer" remote
site:jobs.ashbyhq.com "founding engineer" OR "founding full stack engineer"
site:jobs.lever.co "founding engineer" remote
site:boards.greenhouse.io "software engineer" "full stack" remote startup
site:linkedin.com/jobs "founding engineer" remote United States
site:linkedin.com/jobs "software engineer" "new grad" remote 2026
site:linkedin.com/jobs "AI engineer" remote "member of technical staff"
site:wellfound.com "full stack engineer" remote seed OR "pre-seed"
site:linkedin.com/jobs "forward deployed engineer" remote
site:ycombinator.com/companies jobs "founding engineer" remote
```

**GTM / growth engineering.** A separate job family, and the closest title match in his record: Chronos
*was* an AI-native GTM platform (signal-based targeting, automated outbound, pipeline). These roles sit at
the marketing/engineering seam and are rarely reachable by a generic "software engineer" query, so they
need their own lines.

```
site:linkedin.com/jobs "GTM engineer" OR "go-to-market engineer" remote OR "New York" OR "San Francisco"
site:linkedin.com/jobs "growth engineer" remote United States
site:jobs.ashbyhq.com "growth engineer" OR "GTM engineer"
site:wellfound.com "growth engineer" remote
site:linkedin.com/jobs "forward deployed engineer" OR "AI field engineer" remote
site:jobs.lever.co "forward deployed engineer"
```

Contract and part-time variants for the same tier:

```
site:linkedin.com/jobs "contract software engineer" remote United States
site:wellfound.com "contract engineer" remote
site:linkedin.com/jobs "part time software engineer" OR "fractional engineer" remote
```

### Priority 1: Software Engineering internships (full-stack / backend)

Shawn's strongest and most desired direction. Production depth in TypeScript, Next.js, Python, FastAPI, Postgres, and AWS.

```
site:joinhandshake.com "software engineer intern" summer 2027 remote
site:linkedin.com/jobs "software engineering intern" summer 2027 remote
site:linkedin.com/jobs "backend engineer intern" remote United States
site:indeed.com "software engineer intern" remote "summer 2027"
site:builtin.com "software engineering intern" remote
site:boards.greenhouse.io "software engineer intern" 2027
site:jobs.lever.co "software engineering intern" summer 2027
site:wellfound.com "software engineer intern" remote
site:linkedin.com/jobs "full stack intern" TypeScript remote
site:linkedin.com/jobs "SWE intern" OR "engineering co-op" remote 2027
```

School-year part-time and contract variants:

```
site:indeed.com "part-time software developer" remote contract
site:linkedin.com/jobs "part time software engineer" remote United States
site:wellfound.com "contract engineer" remote part-time
site:linkedin.com/jobs "student developer" OR "junior developer" part-time remote
```

### Priority 2: AI / ML and Agent Engineering internships

Domain expertise: Gemini 2.0, Google ADK multi-agent orchestration, LangChain, applied LLM systems, computer vision, voice AI. This is applied agent engineering, **not** model training or ML research, so skip postings demanding research publications or deep-learning training pipelines.

```
site:linkedin.com/jobs "AI engineer intern" summer 2027 remote
site:linkedin.com/jobs "machine learning engineer intern" remote United States
site:joinhandshake.com "AI intern" OR "artificial intelligence intern" summer 2027
site:boards.greenhouse.io "AI engineer intern" LLM
site:jobs.lever.co "applied AI intern" OR "AI engineering intern"
site:builtin.com "AI engineer intern" remote
site:wellfound.com "AI engineer" intern remote LLM agents
site:linkedin.com/jobs "LLM engineer intern" OR "agent engineer" remote
site:indeed.com "AI automation" intern remote
site:linkedin.com/jobs "computer vision intern" OpenCV remote
```

### Priority 3: IT / Cloud Infrastructure / DevOps

Backed by the Orlando Health contract (Active Directory, 99.9% uptime, SLA-bound support, PowerShell automation) and the Geodo cloud stack (AWS CDK, SQS/Lambda, Aurora, OpenTelemetry). Matches the IT-internship framing on his current CV.

```
site:joinhandshake.com "IT intern" summer 2027 remote
site:linkedin.com/jobs "IT internship" remote United States 2027
site:linkedin.com/jobs "cloud engineer intern" AWS remote
site:dice.com "IT support" remote part-time contract
site:linkedin.com/jobs "DevOps intern" OR "platform engineer intern" remote
site:indeed.com "systems administrator" intern OR entry remote
site:boards.greenhouse.io "infrastructure intern" AWS
site:linkedin.com/jobs "site reliability" intern remote
site:linkedin.com/jobs "technology specialist" OR "technical analyst" remote part-time
```

### Priority 4: Solutions / Sales Engineering and Technical Consulting

Adjacent direction with real supporting evidence: 4th of 20 at the NSEC Florida Regional Sales Engineering Competition, nine years of client-facing founder work, and a CTO role building GTM tooling for sales teams. Strong fit and under-contested by other CS undergraduates.

```
site:linkedin.com/jobs "solutions engineer intern" remote
site:linkedin.com/jobs "sales engineer intern" summer 2027
site:joinhandshake.com "solutions engineering intern" OR "technical consultant intern"
site:builtin.com "solutions engineer" intern remote
site:linkedin.com/jobs "forward deployed engineer" intern OR new grad remote
site:linkedin.com/jobs "technical consultant" intern remote
site:indeed.com "implementation engineer" intern remote
```

### Priority 5: Worth considering (suggested, not yet confirmed with Shawn)

Role shapes his profile fits unusually well but that he did not name during setup. Run these on a `/scrape broad`, and drop the tier if the results do not appeal.

```
site:linkedin.com/jobs "developer relations" intern OR "DevRel intern" remote
site:linkedin.com/jobs "developer advocate" intern remote
site:wellfound.com "founding engineer" remote early-stage
site:linkedin.com/jobs "technical product manager" intern remote
site:linkedin.com/jobs "product engineer" intern remote
site:linkedin.com/jobs "growth engineer" intern remote
```

Why each is worth a look:
- **Developer relations / advocacy** - he already combines production engineering with client-facing communication, which is the exact DevRel blend and is rarely available in an undergraduate
- **Founding engineer at an early-stage startup** - closest match to how he actually works. No longer a scheduling conflict now that Chronos has ended, which is why this shape is promoted to Priority 0 above; the Priority 5 line is kept only for the adjacent titles
- **Technical product management** - nine years of owning scoping, pricing, and client outcomes alongside the build
- **Growth engineer** - GTM platform experience plus full-stack, a narrow and well-paid niche

## Location Filter

Shawn is based in **Inlet Beach, Florida** (Walton County, panhandle) and searches **US-wide, remote-first**. Two different rules apply depending on the term, because he is in class in Florida during fall and spring.

**Ideal:**
- Fully remote, US-based - any term

**Acceptable (any term):**
- Hybrid or on-site in the **San Francisco Bay Area** - SF, Peninsula, South Bay. He splits his time there and
  is present regularly, so treat Bay Area on-site and hybrid as viable year-round, **not** relocation-only
- Hybrid or on-site in Panama City, FL (~30 min)
- Hybrid or on-site in Destin / Fort Walton Beach / Santa Rosa Beach, FL (~45 min)

**Acceptable for a summer internship only (he will relocate for the term):**
- Any other US metro, including Seattle, New York, Austin, Boston, Atlanta, Denver, Chicago
- Florida metros outside the panhandle: Orlando, Tampa, Jacksonville, Miami, Gainesville

**Borderline:**
- Pensacola, FL (~2h) and Tallahassee, FL (~2h) - fine for a summer term or a hybrid role needing on-site presence no more than once a week; too far for a regular school-year commute

**Too far for school-year on-site work:**
- Gainesville, FL (~5h from Inlet Beach) - note this is his *university's* city but he cannot commute there from home; do not treat a Gainesville address as local
- Everything else outside the panhandle

**Flag for discussion:**
- Outside the US, or requiring frequent international travel

## Language Filter

Shawn works in **English only**. Apply `04-job-evaluation.md`'s Language Gate: a posting requiring any language other than English as a job condition is **excluded** before scoring. A posting merely *written* in another language, for a role whose working language is English, is fine. Since English is declared Native, the "declared but lower level than required" FLAG case cannot arise for English.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown". Be stricter than usual about stale internship postings: a Summer 2027 requisition that has been open for months is often already filled through rolling review.

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus:
- `/scrape fulltime` or `/scrape founding` or `/scrape now` -> Priority 0
- `/scrape software` or `/scrape swe` -> Priority 1
- `/scrape ai` or `/scrape ml` -> Priority 2
- `/scrape it` or `/scrape infra` or `/scrape cloud` -> Priority 3
- `/scrape solutions` or `/scrape sales` -> Priority 4
- `/scrape devrel` or `/scrape product` -> Priority 5
- `/scrape part-time` -> the school-year variants under Priority 1 plus the contract lines in Priority 3
- `/scrape broad` -> all five tiers

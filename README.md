# Career Companion

AI agent skill for job search, resume tailoring, and interview prep across frontier tech — space, AI, robotics, drones, defense, and autonomy.

Powered by [Zero G Talent](https://zerogtalent.com) — live openings from 100+ companies via direct ATS integrations. No API key required.

## What It Does

**Find jobs** — Search live openings by keyword, company, location, or employment type. Results include salary ranges, direct apply links, and pagination.

```
"Find me ML engineer roles at SpaceX"
"Remote AI internships"
"What propulsion engineer jobs does Blue Origin have?"
```

**Tailor resumes** — Fetches the full job description, extracts requirements and tech stack, then rewrites bullet points to mirror the JD language. Knows what SpaceX vs. NASA vs. Anthropic actually look for.

```
"Here's my resume — tailor it for this Anthropic role"
"Review my CV for robotics jobs"
```

**Mock interviews** — Company-specific questions derived from the actual job description. Behavioral (STAR), technical, and culture-fit formats. Honest feedback after each answer, debrief at the end.

```
"I have a phone screen at Blue Origin next week, help me prep"
"Run a mock interview for this OpenAI research scientist role"
```

**Salary research** — Aggregates salary data across search results. When salary fields are null, says so honestly.

```
"How much do AI safety researchers make?"
"What's the pay range for senior engineers at Rocket Lab?"
```

## Example Output

```
**1. Sr. Main Engine Propulsion Engineer - Lunar Permanence**
Blue Origin · Greater Seattle Area; Los Angeles, CA; Denver, CO
$145K–$203K/yr · Apply → zerogtalent.com/space-jobs/blue-origin/...

**2. Principal Propulsion Engineer - BE-3U Upgrades**
Blue Origin · Greater Seattle Area; Huntsville, AL
$169K–$237K/yr · Apply → zerogtalent.com/space-jobs/blue-origin/...

**3. Senior Propulsion Test Engineer**
Blue Origin · Lancaster, CA
$145K–$203K/yr · Apply → zerogtalent.com/space-jobs/blue-origin/...

Showing 10 of 346 results
```

Mobile-friendly — designed for Telegram, Slack, and chat interfaces where long messages get truncated.

## Install

### Claude Code

```bash
clawhub install career-companion
```

### Manual

Copy the `career-companion/` folder into your agent's skills directory.

## Companies Covered

| Sector | Companies |
|--------|-----------|
| **Space** | SpaceX, NASA, Blue Origin, Rocket Lab, Boeing, Northrop Grumman, Lockheed Martin, Relativity Space, ULA, L3Harris, Astranis, Planet |
| **AI** | OpenAI, Anthropic, DeepMind, xAI, Cohere, Scale AI, Together AI, Perplexity, Databricks, Cursor |
| **Robotics** | Boston Dynamics, Waymo, Neuralink, Aurora Innovation, IonQ, Rigetti, Helion Energy |
| **Drones & Defense** | Skydio, Anduril, Shield AI, Zipline |

Full list with API slugs: [`references/companies.md`](career-companion/references/companies.md)

## API

Public JSON API — no auth required.

| Endpoint | Purpose |
|----------|---------|
| `GET /api/jobs/search?q=...&company=...&limit=10` | Search jobs |
| `GET /api/job?company={slug}&jobId={externalId}` | Full job description |

Params: `q`, `company`, `location`, `employmentType`, `remote`, `limit` (default 10, max 50), `offset`.

Full schema and response examples: [`references/api.md`](career-companion/references/api.md)

## Skill Structure

```
career-companion/
  SKILL.md              # Agent instructions — workflow, output rules, domain knowledge
  references/
    api.md              # API endpoints, parameters, response schema
    companies.md        # Company slugs for the company= filter
```

## License

MIT

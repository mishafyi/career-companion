# SeekerClaw Career Companion

Your AI career coach — find jobs, build standout resumes, practice interviews, and plan your next move.

SeekerClaw Career Companion helps you navigate every stage of the job search: from exploring career paths and identifying skills gaps, to tailoring application materials, preparing for interviews, and negotiating offers. Built for AI agents — works in Claude Code, Telegram, Slack, and any chat interface.

## What It Does

### Find Jobs

Search live openings by keyword, company, location, or employment type. Results include salary ranges and direct apply links.

```
"Find me ML engineer roles at SpaceX"
"Remote AI internships"
"What propulsion engineer jobs does Blue Origin have?"
"Show me robotics jobs in California"
```

### Resumes, Cover Letters & LinkedIn

Review and tailor application materials for specific roles. Fetches the actual job description, extracts requirements, and rewrites your bullets to mirror the JD language.

```
"Here's my resume — tailor it for this Anthropic role"
"Review my CV for robotics jobs"
"Help me write a cover letter for this position"
"What should I highlight on my LinkedIn for AI roles?"
```

### Interview Prep

Company-specific mock interviews derived from real job descriptions. Behavioral (STAR), technical, and culture-fit formats. Honest feedback after each answer, full debrief at the end.

```
"I have a phone screen at Blue Origin next week"
"Run a mock interview for this OpenAI research scientist role"
"What questions should I expect at NASA?"
```

### Salary & Negotiation

Research compensation ranges across roles and companies. Get role-specific talking points for salary negotiations.

```
"How much do AI safety researchers make?"
"What's the pay range for senior engineers at Rocket Lab?"
"Help me negotiate this offer"
```

### Career Planning

Explore career paths, identify transferable skills, find adjacent roles, and plan transitions.

```
"I'm a mechanical engineer — what space jobs could I transition to?"
"What skills do I need to break into robotics?"
"Help me figure out which Anthropic role fits my background"
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

Designed for mobile — scannable in Telegram, Slack, and chat where long messages get truncated.

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

Public JSON API — no auth required. Job data from [Zero G Talent](https://zerogtalent.com).

| Endpoint | Purpose |
|----------|---------|
| `GET /api/jobs/search?q=...&company=...&limit=10` | Search jobs |
| `GET /api/job?company={slug}&jobId={externalId}` | Full job description |

Params: `q`, `company`, `location`, `employmentType`, `remote`, `limit` (default 10, max 50), `offset`.

Full schema: [`references/api.md`](career-companion/references/api.md)

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

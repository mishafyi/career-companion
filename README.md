# SeekerClaw Career Companion

Your AI Career Companion for frontier tech — AI, space, robotics, and drones.

A [SeekerClaw](https://seekerclaw.com) skill that searches live job openings, helps tailor resumes for specific roles, and runs mock interviews.

Powered by [Zero G Talent](https://zerogtalent.com) — a job board aggregating live openings from hundreds of frontier tech companies via direct ATS integrations.

> **Looking for the Claude Code version?** Install via ClawHub: `clawhub install career-companion`

## What It Does

| Capability | Description |
|-----------|-------------|
| **Find Jobs** | Search live openings at SpaceX, OpenAI, Anthropic, NASA, Boston Dynamics, and 100+ more companies |
| **Resume Help** | Review, critique, and tailor resumes for frontier tech roles using actual job description language |
| **Interview Prep** | Mock interviews with company-specific questions, STAR method coaching, and honest feedback |
| **Salary Research** | Aggregate salary data across roles and companies |

## Install

### SeekerClaw
```bash
seekerclaw install career-companion
```

### Manual
Copy the `career-companion/` folder into your agent's `skills/` directory.

## Usage

Just ask naturally:

- "Find me ML engineer roles at SpaceX"
- "Help me prepare for an Anthropic interview"
- "Review my resume for robotics jobs"
- "How much do AI safety researchers make?"
- "What remote AI internships are available?"

The skill chains capabilities automatically — searching jobs, fetching descriptions, tailoring resumes, and running interviews in sequence.

## Companies Covered

**Space:** SpaceX, NASA, Blue Origin, Rocket Lab, Boeing, Northrop Grumman, Lockheed Martin, Relativity Space, ULA, L3Harris, Astranis, Planet

**AI:** OpenAI, Anthropic, DeepMind, xAI, Cohere, Scale AI, Together AI, Perplexity, Databricks, Cursor

**Robotics:** Boston Dynamics, Waymo, Neuralink, Aurora Innovation, IonQ, Rigetti, Helion Energy

**Drones:** Skydio, Anduril, Shield AI, Zipline

## API

Uses the public [Zero G Talent API](https://zerogtalent.com) — no authentication required.

- `GET /api/jobs/search` — Search jobs by keyword, company, location, type
- `GET /api/job?company={slug}&jobId={id}` — Full job description

## License

MIT

# Zero G Talent API Reference

All endpoints are public — no authentication required.

## Search Jobs

```
GET https://zerogtalent.com/api/jobs/search
```

### Parameters

| Param | Type | Default | Description |
|-------|------|---------|-------------|
| `q` | string | — | Full-text + fuzzy keyword search |
| `company` | string | — | Company slug filter |
| `location` | string | — | Location slug (e.g., `california`, `remote`, `texas`, `new-york`) |
| `employmentType` | string | — | `full-time`, `internship`, `part-time`, `contract` |
| `remote` | string | — | `true` for remote-only jobs |
| `limit` | number | 20 | Results per page (max 50) |
| `offset` | number | 0 | Pagination offset |
| `format` | string | — | Set to `md` for markdown output (recommended for agents) |

### Markdown Response (`format=md`)

Returns pre-formatted markdown — present directly to users:

```
**Machine Learning Engineer** at Waymo
Mountain View, California, United States | Full Time | $170,000–$216,000/year
[View & Apply](https://zerogtalent.com/space-jobs/waymo/machine-learning-engineer-7455853)

**Research Scientist, Alignment** at Anthropic
San Francisco, CA | Full-time | $200,000–$350,000/year
[View & Apply](https://zerogtalent.com/space-jobs/anthropic/research-scientist-alignment)

Page 1/5 | 42 results
Next: offset=20
```

### JSON Response (default)

Without `format=md`, returns JSON with full job objects. Useful for programmatic salary aggregation.

```json
{
  "jobs": [
    {
      "title": "Research Scientist, Alignment",
      "slug": "research-scientist-alignment",
      "externalId": "abc-123-def",
      "location": "San Francisco, CA",
      "remote": false,
      "employmentType": "Full-time",
      "category": "Research",
      "isActive": true,
      "salaryMin": 200000,
      "salaryMax": 350000,
      "salaryCurrency": "USD",
      "salaryInterval": "YEAR",
      "company": {
        "name": "Anthropic",
        "slug": "anthropic",
        "logoUrl": "https://zerogtalent.com/logos/anthropic.png"
      }
    }
  ],
  "total": 42,
  "hasMore": true,
  "pagination": { "offset": 0, "limit": 20, "total": 42 }
}
```

## Get Job Description

```
GET https://zerogtalent.com/api/job?company={company-slug}&jobId={externalId}&format=md
```

Returns the complete job as markdown with title, company, location, salary, full description text, and links to related roles at the same company.

Without `format=md`, returns the full JSON job object including the HTML `description` field.

**Important:** Use `externalId` from search results, never the `slug`. The `slug` is for URL display only.

## Job Detail Page URLs

Link to the Zero G Talent job page (not the direct ATS URL) for a better experience:

```
https://zerogtalent.com/space-jobs/{company-slug}/{job-slug}
```

Both `company-slug` (from `company.slug`) and `job-slug` (from `slug`) come from the search response.

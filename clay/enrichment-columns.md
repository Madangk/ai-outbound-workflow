# Clay enrichment

> **Note:** Example column setup for this repo. Column names are illustrative.

Clay receives the record from HubSpot and adds the context the prompt needs. Each column has one job.

| Column | Source / method | Used for |
|---|---|---|
| Company domain | From HubSpot | Key for every other lookup |
| Company size and industry | Clay company enrichment | Fit check and tone of message |
| Contact title and seniority | Clay person enrichment | Choosing the problem to lead with |
| Signal | From the HubSpot trigger | First line of the message |
| Signal detail | Web research / job posts / news | Making the first line specific |
| Tech stack hints | Clay technographics | Picking the right product angle |
| Product angle | Formula or lookup table | Mapping the signal to what we solve |
| AI draft | Claude prompt (see [`../prompts`](../prompts/)) | The message itself |
| Send to Slack | Clay → Slack integration | Review step |

## Fit filter

Before the Claude step runs, a simple filter stops records that are a poor fit (wrong size, wrong region, missing contact). This saves AI credits and keeps the Slack channel clean.

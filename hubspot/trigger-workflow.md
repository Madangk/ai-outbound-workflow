# HubSpot trigger

> **Note:** Example setup for this repo. Use the signals that matter for your product.

## How it is set up

1. In HubSpot, create a **workflow** based on contacts or companies.
2. Set the **enrollment trigger** to the signal you care about.
3. Add a **webhook action** that sends the record to a Clay table.
4. Optionally, set a property such as `outbound_status = enriched` so the record does not enter twice.

## Example signals

These are common signals for B2B infrastructure and SaaS selling:

- A contact downloads content or visits the pricing page
- An inbound lead goes cold and is ready to recycle
- A target account starts hiring for a relevant role
- A target account raises funding or announces expansion
- A known champion changes jobs to a new company

Pick a small number of strong signals. Too many triggers turn this back into spam.

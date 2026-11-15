# Personalisation prompt

> **Note:** This is a cleaned-up example version of the prompt, written for this repo. It follows the same structure as the one used in the live workflow.

The prompt receives one enriched record from Clay and returns a short first-touch message plus a one-line reason for the seller.

## Inputs (from Clay)

| Variable | Example |
|---|---|
| `{{first_name}}` | Priya |
| `{{title}}` | Head of Data Engineering |
| `{{company}}` | Northwind Payments (fictional) |
| `{{industry}}` | Fintech |
| `{{signal}}` | Hiring 3 senior data engineers |
| `{{signal_detail}}` | Job posts mention real-time analytics and query latency |
| `{{product_angle}}` | How our product helps with that problem |

## Prompt

```
You are helping an enterprise account executive write the first message to a prospect.

Prospect: {{first_name}}, {{title}} at {{company}} ({{industry}}).
Signal: {{signal}}. Detail: {{signal_detail}}.
What we help with: {{product_angle}}.

Write a first-touch message that:
- opens with the signal, in plain words, in the first sentence
- connects the signal to one problem this person likely owns
- offers one specific, low-effort next step (a short call, a benchmark, a resource)
- is 3 to 4 sentences, under 80 words
- sounds like a person wrote it: no flattery, no buzzwords, no exclamation marks
- does not invent facts that are not in the inputs

Then, on a new line starting with "WHY:", give the seller one sentence on why this account is worth contacting now.

If the signal is weak or the inputs are missing, reply only with "SKIP" and the reason.
```

## Rules behind the prompt

- **Signal in the first line.** The reader should know in one sentence why they are getting the message.
- **One problem, one ask.** Listing every feature lowers reply rates.
- **No made-up facts.** The model may only use what Clay found.
- **A SKIP option.** It's better to send nothing than a generic message.

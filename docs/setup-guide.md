# Setup guide

How to rebuild this workflow in your own stack. You need access to HubSpot (workflows), Clay, an Anthropic API key (or Clay's built-in AI column), and a Slack workspace.

## Steps

1. **Pick 2 or 3 signals** that tell you an account is worth contacting now. See [`../hubspot/trigger-workflow.md`](../hubspot/trigger-workflow.md).
2. **Build the HubSpot workflow** with that trigger and a webhook to Clay.
3. **Create the Clay table** with the columns in [`../clay/enrichment-columns.md`](../clay/enrichment-columns.md). Add the fit filter before the AI step.
4. **Add the AI column** with the prompt in [`../prompts/personalisation-prompt.md`](../prompts/personalisation-prompt.md). Test it on 10 to 20 records and tune the rules until the drafts sound like you.
5. **Connect Slack** so each draft posts to a review channel with the key facts.
6. **Review daily.** Approve, edit or skip. Note the edits you make most often and fold them back into the prompt.

## Tips

- Start small. One signal and one segment, done well, beats ten done badly.
- Keep the human review step. It protects your domain and your reputation.
- Track replies by signal type, so you know which signals are worth keeping.

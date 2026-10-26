# The front-end and back-end agents propose build prompts. A prompt is sent only after the owner approves the exact text.

- Date: 2026-10-06
- Decided by: Shelly
- Why: Sending a prompt spends build credits and changes the main project. A person should see the exact words before that happens.
- Replaces: Proposal only, with no path to send. The agents may now send to the main project once the owner approves the prompt. A/B test variants go to a remix, so the control stays clean.
- Note: the gate is written into the agent instructions. It is not enforced by tool permissions, so the owner still reviews each run.

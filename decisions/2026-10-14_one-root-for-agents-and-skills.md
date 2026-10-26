# One root folder loads the agents and skills. They are not installed globally.

- Date: 2026-10-14
- Decided by: Shelly
- Why: One self-contained folder is easier to reason about, review, and share. The root instructions file routes to context, rules, skills, agents, projects, and decisions.
- Replaces: Agents, skills, and commands symlinked globally into every session.
- Also decided the same day: two roles that only give advice (design and product management) are skills run in the main chat, not agents.

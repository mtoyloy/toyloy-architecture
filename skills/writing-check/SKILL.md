---
name: writing-check
description: Use when the owner says "writing check", "does this sound like AI", "clean this up", "make this sound like me", "check for AI-isms", or hands over a draft (email, LinkedIn, investor update, landing copy) to audit before it goes out. Checks the text against their voice rules and a short list of AI patterns, then returns findings and a light rewrite.
argument-hint: "[paste the draft, or a file path] [format: linkedin | email | investor | blog | docs]"
---

## Steps
1. Read the owner's voice rules (below). They are the source of truth.
2. Get the draft and the format. If the format is missing, treat it as an email.
3. Audit, then rewrite lightly. Keep the owner's meaning. Do not rewrite from scratch.
4. Return the output below. Nothing is sent or published by this skill.

## Voice rules (the "never" list)
- Em dashes, or en dashes used as em dashes. Use a comma, a period, or parentheses.
- "It is not just X, it is Y" and other setup and payoff constructions.
- Rule-of-three lists in prose ("clear, concise, and compelling").
- Filler adjectives and consultant-speak: robust, seamless, leverage, delve, landscape, crucial, vital, testament, unlock, elevate, navigate, tapestry, "in today's world."
- Bolding half a sentence for emphasis inside prose.
- Restating what someone just said before responding to it.
- Closing with a summary of what was already written above.
- Contractions in full sentences, especially in decks and official materials. Short headlines, footers, and casual notes may use them.

## What else to flag
- embark, realm, paradigm, beacon, pivotal, game-changer, utilize, holistic, actionable, synergy, cutting-edge, comprehensive, showcasing, "deep dive", "worth noting".
- Clusters of these in one paragraph: harness, foster, streamline, empower, bolster, resonate, facilitate, nuanced, multifaceted, ecosystem, myriad, cornerstone, transformative.
- Chatbot leftovers: "Certainly!", "Great question", "I hope this helps", "As an AI".
- Vague attribution ("experts say") and inflated significance ("a pivotal moment").
- Uniform paragraph length, a generic closing line, hedges like "could potentially".
- Do not flag an em dash inside a quote or a name.

## Strictness by format
- LinkedIn: strict on vocabulary, relaxed on structure.
- Email: all rules at full strength.
- Investor: extra strict on promotional words and inflated claims. Numbers need a source.
- Blog: all rules at full strength.
- Docs: relaxed. Clarity over voice.

## Output
- Verdict: clean, light fixes, or heavy rewrite.
- Findings table: severity, exact text, why, fix. P0 = credibility killers (chatbot leftovers, invented claims). P1 = obvious AI smell. P2 = polish.
- The revised draft.
- What changed, in 3 bullets at most.
- End with one test: would the owner say this out loud? Say yes or no and why.

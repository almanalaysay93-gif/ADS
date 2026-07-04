---
description: Service Ad — generate a presenter Shorts ad prompt-pack (title, description, 3 image + 3 Omni video prompts) for a company's priced service via the service-ad-promo subagent
argument-hint: "[company] - [service] - [price]"
---

Launch the **service-ad-promo** subagent (Agent tool, `subagent_type: service-ad-promo`) to produce the full service-ad Shorts prompt-pack.

Ad input (pass through verbatim):

$ARGUMENTS

Rules:
- If `$ARGUMENTS` is missing the company, the service, or the price, ask once for the missing piece(s), then launch.
- Let the subagent run its own flow: read Obsidian channel memory + per-company memory → generate the four-section `.md` (Title · Description · Image Prompts 1–3 · Video Prompts 4–6 in Omni prose) → write it to the Obsidian vault → append to memory.
- Do NOT print the prompt-pack `.md` content in chat. Only confirm: the saved vault file path + one-line recap of key decisions (hook, DR arc, CTA). The prompts live in the vault only.

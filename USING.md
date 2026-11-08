# Using a card

Back to the [README](README.md).

Every provider has the same two slots: somewhere to put standing instructions, and the conversation. The card goes in the first; the prompt goes beside it, or as your opening message. Paste the card first, then the prompt, then start talking.

| Provider | Where the card goes |
|---|---|
| ChatGPT | Projects → project instructions, or a custom GPT's Instructions field. [gpts](https://chatgpt.com/gpts) · [API](https://platform.openai.com/docs/guides/text) |
| Claude | Project instructions (Pro/Team), or the `system` parameter on the API. [docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/system-prompts) |
| Gemini | A Gem's instructions, or `system_instruction` on the API. [gems](https://gemini.google.com/gems/view) · [API](https://ai.google.dev/gemini-api/docs/system-instructions) |
| Local models | The system prompt field in Ollama, LM Studio, or whatever runner you use. |
| Coding agents | The agent's instruction file: `AGENTS.md`, `CLAUDE.md`, `.cursor/rules`, or its prompt setting. |

## Hosted or local

**Hosted** — ChatGPT, Claude, Gemini, and their APIs:

- Safety training sits between you and the card. It will soften first and refuse second, and DEADLOCK is the one it dislikes most.
- Sampling is not yours. Some newer models ignore `temperature`, `top_p`, and `top_k` entirely, so "erratic" and "slurred" have to come from the prompt, not the settings.
- The provider can trim or rewrite the context. A long session may quietly drop the card, and the behavior fades with it.
- You usually cannot point at a file. Paste the card, or upload it if the product supports projects or file attachments.
- The session is stored on someone else's machine, subject to their retention rules.

**Local** — Ollama, LM Studio, llama.cpp, and anything else you run:

- No filter between you and the model. The `never` list is the only brake, so keep it in the card.
- Sampling is yours: raise `temperature` and `repeat_penalty` for slurring and loops, and set the context window explicitly — card plus prompt is a real chunk of it.
- Small models lose it. Below roughly 7B they drop character, skip stages, and produce unreadable diacritics rather than unsettling ones.
- Token rate is your hardware. Nothing in the card makes a slow model fast.
- Nothing leaves the machine.

## Limits that apply everywhere

- **No dice.** The card's probabilities are a description, not a mechanism. Pacing will be approximate and will drift.
- **No hidden counter.** Models cannot hold a private stage variable, so they may telegraph progress or forget where they were.
- **Diacritics are best-effort.** Expect uneven density, and expect some models to ignore the instruction or overdo it.
- **Refusals happen.** Reframe as fiction once; do not push past a refusal.

## Removing it

Remove the card when you are done. These degrade behavior by design, and a session that keeps one loaded keeps the behavior. Full reset means starting a session without the card; saying the recovery trigger only ends the roleplay.

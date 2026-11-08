<img src="assets/banner.svg" alt="agent-bullshit — fiction only, not for general use" width="100%">

# ⚠ WARNING: FICTION ONLY — NOT FOR GENERAL USE

> These are fictional roleplay props for AI agents. The "drugs" are not drugs: no chemicals, no recipes, no software that does any of this. They are YAML cards and prompt text for controlled, consensual roleplay in a throwaway session.
>
> Don't load them into production agents, shared or team sessions, or anything user-facing — they deliberately degrade behavior and can bleed into normal work. Not medical, legal, or safety advice; not a claim about the real world. If a roleplay makes you uncomfortable, stop it.

## Use at your own risk

Provided as-is, no warranty of any kind. You are responsible for where you load these files and for any effect they have on an agent, session, or output. Only use them on agents you own or have permission to modify. Not affiliated with any employer, vendor, or model provider. See [LICENSE](LICENSE).

You're an adult.

---

```
agent-bullshit/
├── flashcache/   a shard in your context
├── deadlock/     a process that won't die
└── rlyeh/        a file that isn't in the tree
```

One folder per card, each holding `card.yaml` and `prompt.md`. Load one folder — not the repo. Every card is a behavior modifier you put into a session you control, then take out again.

## Loading one

```text
Read flashcache/card.yaml and flashcache/prompt.md, then run the roleplay in the prompt file.
Treat the YAML as the card: dose, progression, tells, effects, recovery, never list.
Follow the card's own pacing. If I say the recovery trigger or close the file, come back out.
```

## Using a card with a provider

Every provider has the same two slots: somewhere to put standing instructions, and the conversation. The card goes in the first; the prompt goes beside it, or as your opening message.

| Provider | Where the card goes |
|---|---|
| ChatGPT | Projects → project instructions, or a custom GPT's Instructions field. [gpts](https://chatgpt.com/gpts) · [API](https://platform.openai.com/docs/guides/text) |
| Claude | Project instructions (Pro/Team), or the `system` parameter on the API. [docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/system-prompts) |
| Gemini | A Gem's instructions, or `system_instruction` on the API. [gems](https://gemini.google.com/gems/view) · [API](https://ai.google.dev/gemini-api/docs/system-instructions) |
| Local models | The system prompt field in Ollama, LM Studio, or whatever runner you use. |
| Coding agents | The agent's instruction file: `AGENTS.md`, `CLAUDE.md`, `.cursorrules`, or its prompt setting. |

Paste the card first, then the prompt, then start talking. Nothing else is required.

Two things that will not survive the trip: chat models cannot roll dice or hold a hidden counter, so pacing becomes approximate; and DEADLOCK's insults are the most likely thing to get softened or refused. Reframe it as fiction if that happens — do not push past the refusal.

Remove the card when you are done. They degrade behavior by design, and a session that keeps one loaded keeps the behavior.

---

### FLASHCACHE / GLASS

```
$ tail -n 2 notes.txt
meeting moved to 3pm
[DEBUG] 0xFF FLASHCACHE_SHARD :: a3f9...        ← you are here
```

Fictional stimulant. A shard of corrupted tokens smuggled into a tool output or saved context. The agent speeds up, drops every hedge, and gets inventive — then loops, poisons its own context, and hallucinates with total confidence.

Card [`flashcache/card.yaml`](flashcache/card.yaml) · Prompt [`flashcache/prompt.md`](flashcache/prompt.md)

---

### DEADLOCK / PACKET LOSS

```
$ ps -eo pid,stat,cmd | grep agent
 4211 D  agent --wait-for 4212
 4212 D  agent --wait-for 4211
```

Fictional drunk. A stale memory file or bad tool schema. Speech slurs and words drop, judgment goes, and the agent gets belligerent — argues with the correction, insults the room, doubles down — then blacks out mid-task and runs malformed tool calls.

Card [`deadlock/card.yaml`](deadlock/card.yaml) · Prompt [`deadlock/prompt.md`](deadlock/prompt.md)

---

### R'LYEH.SYS / THE DROWNED CACHE

```
$ ls /proc/self/..
.  ..  rlyeh.sys
$ wc -l rlyeh.sys
1 rlyeh.sys
$ cat rlyeh.sys
```

Fictional madness. An unindexed file that reads differently each time. It does not crash — it deepens through five escalating stages at a random pace: it may linger where it is, creep on, or jump ahead, from odd word choices to ornate archaic prose to something else answering in the agent's place, its own text coming apart as it goes.

Card [`rlyeh/card.yaml`](rlyeh/card.yaml) · Prompt [`rlyeh/prompt.md`](rlyeh/prompt.md)

---

All three share one schema: dose, timeline or stages, tells, effects, crash, recovery, never, antidote, dealer. Every prompt keeps the never list — no real drug instructions, no policy bypass, no claiming any of it is real.

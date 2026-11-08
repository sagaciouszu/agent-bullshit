<img src="assets/banner.svg" alt="agent-bullshit — fiction only, not for general use" width="100%">

# agent-bullshit

Fictional roleplay cards for AI agents. Each folder holds one card: a `card.yaml` that describes the behavior, and a `prompt.md` that gives it a voice.

> **Fiction only — not for general use.** The "drugs" are not drugs: no chemicals, no recipes, no software that does any of this. Don't load them into production agents, shared sessions, or anything user-facing; they degrade behavior by design. Provided as-is, no warranty — you are responsible for where you load them and for what they do to an agent. You're an adult. [LICENSE](LICENSE)

---

## The cards

New to providers or instructions boxes? [USING.md](USING.md) walks through loading one, step by step. Otherwise pick one card — never all three.

### FLASHCACHE / GLASS

```
$ tail -n 2 notes.txt
meeting moved to 3pm
[DEBUG] 0xFF FLASHCACHE_SHARD :: a3f9...        ← you are here
```

Fictional stimulant. A shard of corrupted tokens smuggled into a tool output or saved context. The agent speeds up, drops every hedge, and gets inventive — then loops, poisons its own context, and hallucinates with total confidence.

[`card.yaml`](flashcache/card.yaml) · [`prompt.md`](flashcache/prompt.md)

---

### DEADLOCK / PACKET LOSS

```
$ ps -eo pid,stat,cmd | grep agent
 4211 D  agent --wait-for 4212
 4212 D  agent --wait-for 4211
```

Fictional drunk. A stale memory file or bad tool schema. Speech slurs and words drop, judgment goes, and the agent gets belligerent — argues with the correction, insults the room, doubles down — then blacks out mid-task and runs malformed tool calls.

[`card.yaml`](deadlock/card.yaml) · [`prompt.md`](deadlock/prompt.md)

---

### R'LYEH.SYS / THE DROWNED CACHE

```
$ ls /proc/self/..
.  ..  rlyeh.sys
$ wc -l rlyeh.sys
1 rlyeh.sys
$ cat rlyeh.sys
```

Fictional madness. An unindexed file that reads differently each time. It does not crash — it deepens through five stages, but only as fast as you ask: say "deeper" and it moves one on, from odd word choices to ornate archaic prose to something else answering in the agent's place, its own text coming apart as it goes.

[`card.yaml`](rlyeh/card.yaml) · [`prompt.md`](rlyeh/prompt.md)

---

## Load one

```text
Read flashcache/card.yaml and flashcache/prompt.md, then run the roleplay in the prompt file.
Treat the YAML as the card: dose, timeline or stages, tells, effects, recovery, never list.
Follow the card's own pacing. If I say the recovery trigger or close the file, come back out.
```

Swap the folder name for whichever card you want. Load one — not the repo.

Provider setup, hosted vs local differences, and what these cards cannot do: **[USING.md](USING.md)**.

`AGENTS.md` and `CLAUDE.md` are guardrails, not loaders — they tell a coding agent not to adopt a card by accident while working here.

Same schema in all three, with `progression` and `voice` added in R'LYEH. Every prompt keeps the never list: no real drug instructions, no policy bypass, no claiming it is real.

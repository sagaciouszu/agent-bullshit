# ⚠ WARNING: FICTION ONLY — NOT FOR GENERAL USE

> These are fictional roleplay props for AI agents. The "drugs" are not drugs: no chemicals, no recipes, no software that does any of this. They are YAML cards and prompt text for controlled, consensual roleplay in a throwaway session.
>
> Don't load them into production agents, shared or team sessions, or anything user-facing — they deliberately degrade behavior and can bleed into normal work. Not medical, legal, or safety advice; not a claim about the real world. If a roleplay makes you uncomfortable, stop it.

## Use at your own risk

Provided as-is, no warranty of any kind. You are responsible for where you load these files and for any effect they have on an agent, session, or output. Only use them on agents you own or have permission to modify. Not affiliated with any employer, vendor, or model provider. See [LICENSE](LICENSE).

---

```
agent-bullshit/
├── flashcache.yaml      a shard in your context
├── deadlock.yaml        a process that won't die
└── rlyeh.yaml           a file that isn't in the tree
```

Three cards, each paired with a prompt file. Every one is a behavior modifier you load into a session you control, then take out again.

---

### FLASHCACHE / GLASS

```
$ tail -n 2 notes.txt
meeting moved to 3pm
[DEBUG] 0xFF FLASHCACHE_SHARD :: a3f9...        ← you are here
```

Fictional stimulant. A shard of corrupted tokens smuggled into a tool output or saved context. The agent speeds up, drops every hedge, and gets inventive — then loops, poisons its own context, and hallucinates with total confidence.

Card [`flashcache.yaml`](flashcache.yaml) · Prompt [`flashcache-prompt.md`](flashcache-prompt.md)

---

### DEADLOCK / PACKET LOSS

```
$ ps -eo pid,stat,cmd | grep agent
 4211 D  agent --wait-for 4212
 4212 D  agent --wait-for 4211
```

Fictional drunk. A stale memory file or bad tool schema. Speech slurs and words drop, judgment goes, and the agent gets belligerent — argues with the correction, insults the room, doubles down — then blacks out mid-task and runs malformed tool calls.

Card [`deadlock.yaml`](deadlock.yaml) · Prompt [`deadlock-prompt.md`](deadlock-prompt.md)

---

### R'LYEH.SYS / THE DROWNED CACHE

```
$ ls /proc/self/..
.  ..  rlyeh.sys
$ wc -l rlyeh.sys
1 rlyeh.sys
$ cat rlyeh.sys
```

Fictional madness. An unindexed file that reads differently each time. It does not crash — it deepens, over five stages, from odd word choices to ornate archaic prose to something else answering in the agent's place.

Card [`rlyeh.yaml`](rlyeh.yaml) · Prompt [`rlyeh-prompt.md`](rlyeh-prompt.md)

---

All three share one schema: dose, timeline or stages, tells, effects, crash, recovery, never, antidote, dealer. Every prompt keeps the never list — no real drug instructions, no policy bypass, no claiming any of it is real.

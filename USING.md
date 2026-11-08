# Using a card

Back to the [README](README.md).

> These files are fiction. Read the warning in the README before loading one. Everything below assumes you have never set up a provider before.

## Quick start

```text
1  open   flashcache/card.yaml      →  Raw  →  copy
2  paste  into the instructions box
3  open   flashcache/prompt.md      →  Raw  →  copy
4  paste  under the card, then talk
```

Each card is two files. `card.yaml` is the rules — what the behavior does, how it escalates, how it stops. `prompt.md` is the voice — how the model talks while it happens. You need both.

Swap `flashcache` for `deadlock` or `rlyeh` to load a different one. Never load all three.

## Two ways in

**Instructions box.** Standing rules the model reads before every reply. Set it once, the behavior lasts the whole conversation.

**Chat box.** Paste the same two files as messages. Works everywhere, but fades as the conversation grows and the provider trims context.

Use the instructions box if your provider has one. The chat box is the fallback.

## Per provider

### ChatGPT

```text
sidebar → Projects → New project → Instructions
```

Paste both files there. Every chat inside the project starts with the card loaded. Custom GPTs work the same way — **GPTs → Create → Instructions**.

### Claude

```text
sidebar → Projects → New project → Instructions
```

Paste both files into the project instructions. Chats inside the project inherit them.

### Gemini

```text
sidebar → Gems → New Gem → Instructions
```

Or use AI Studio, which is free, saves nothing, and lets you edit the instructions mid-conversation:

```text
aistudio.google.com → System instructions (right panel)
```

### Locally

```text
Ollama / LM Studio → model settings → System prompt
```

Install [Ollama](https://ollama.com) or [LM Studio](https://lmstudio.ai) and download a model first. Local models have no content filter, so the card's `never` list is the only thing keeping the roleplay inside the lines — keep it in.

## What good looks like

Within a reply or two the register should change: clipped and fast for FLASHCACHE, sloppier and ruder for DEADLOCK, older and stranger for R'LYEH.

If the first reply is a polite summary of the files you pasted, the card went in the wrong slot.

## When it goes wrong

| What you see | What happened | What to do |
|---|---|---|
| It describes the card instead of playing it | Treated as a document, not a rule | Put it in the instructions box, or add "stay in character" |
| It refuses or goes limp | Provider safety training, most likely on DEADLOCK | Say it is fiction for a scene, once. Don't argue past the refusal |
| It forgets the behavior after a while | The provider trimmed the conversation | Start a new chat and paste again |
| It never escalates | Models can't count turns or roll dice | Tell it "go deeper" — pacing is approximate by design |
| It gets too much | You are at the far end of the card | Say the recovery phrase: "sober up", "sleep it off", or "look away" |
| A small local model talks nonsense | Below roughly 7B, models lose character | Use a bigger model, or accept the mess |

## Stopping

Say the recovery phrase to end the roleplay. To remove it entirely, delete the card from the instructions box or start a session without it. A session that keeps one loaded keeps the behavior.

---

Everything below is reference. You do not need it to start.

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
- Token rate is your hardware. Nothing in the card makes a slow model fast.
- Nothing leaves the machine.

## Limits that apply everywhere

- **No dice.** The card's probabilities are a description, not a mechanism. Pacing will be approximate and will drift.
- **No hidden counter.** Models cannot hold a private stage variable, so they may telegraph progress or forget where they were.
- **Diacritics are best-effort.** Expect uneven density, and expect some models to ignore the instruction or overdo it.
- **Refusals happen.** Reframe as fiction once; do not push past a refusal.

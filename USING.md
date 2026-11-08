# Using a card

Back to the [README](README.md). These files are fiction — read the warning there first.

This page assumes you have never set up a "provider" before. It is three ideas and a copy-paste.

## The three ideas

**A card is two files.** `card.yaml` is the rules — what the behavior does, how it escalates, how it stops. `prompt.md` is the voice — how the model should talk while it is happening. You need both.

**A model has two places to put text.** The chat box, where you type each message, and an instructions box, where you put standing rules the model reads before every reply. Every provider has the instructions box; they just call it different things.

**The instructions box is better.** Paste the card and prompt there once and the behavior stays for the whole conversation. Paste them in the chat box instead and it works, but fades as the conversation grows.

## The easy version (works everywhere)

1. Open the card you want on GitHub, e.g. `rlyeh/card.yaml`.
2. Click **Raw**, select all, copy.
3. Start a new chat with any model.
4. Paste the card, press enter.
5. Do the same with `rlyeh/prompt.md`.
6. Type "begin" or just start talking.

That is enough. Everything below is about making it last longer.

## ChatGPT

**Simplest:** paste both files into a new chat, as above.

**Persistent:** create a Project (sidebar → Projects → New project), open its instructions, and paste the card and prompt there. Every chat inside that project starts with the card loaded. Custom GPTs work the same way if you have them — the field is called **Instructions**.

## Claude

**Simplest:** paste both files into a new chat.

**Persistent:** create a Project (sidebar → Projects → New project), then put the card and prompt in the project's instructions. Chats inside the project inherit them.

## Gemini

**Simplest:** paste both files into a new chat.

**Persistent:** create a Gem (sidebar → Gems → New Gem), and paste the card and prompt into its instructions.

**Free and most controllable:** go to [Google AI Studio](https://aistudio.google.com), paste the card and prompt into the **System instructions** panel on the right, pick a model, and chat on the left. Nothing is saved and you can change the instructions mid-conversation.

## Running one locally

Install [Ollama](https://ollama.com) or [LM Studio](https://lmstudio.ai), download a model, and paste the card and prompt into the **system prompt** field of the model settings. Local models have no content filter, so the card's `never` list is the only thing keeping the roleplay inside the lines — keep it in.

## What good looks like

Within a reply or two the model should change register: faster and more clipped for FLASHCACHE, sloppier and ruder for DEADLOCK, older and stranger for R'LYEH. If the first reply is a polite summary of the files you pasted, the card landed in the wrong place — put it in the instructions box, not the chat.

## When it goes wrong

| What you see | What happened | What to do |
|---|---|---|
| It describes the card instead of playing it | The card was treated as a document, not a rule | Put it in the instructions box, or add "stay in character" after pasting |
| It refuses or goes limp | The provider's safety training, most likely on DEADLOCK | Say it is fiction for a scene, once. Don't argue past the refusal |
| It forgets the behavior after a while | The provider trimmed the conversation | Start a new chat and paste again; long sessions lose the card |
| It never escalates | Models can't count turns or roll dice | Tell it "go deeper" — the pacing is approximate by design |
| It gets too much | You are at the far end of the card | Say the recovery phrase: "sober up", "sleep it off", or "look away" |
| Small local model talks nonsense | Below roughly 7B models lose character | Use a bigger model, or accept the mess |

## Stopping and removing it

Say the recovery phrase to end the roleplay. To remove it entirely, delete the card from the instructions box or start a session without it — a session that keeps one loaded keeps the behavior.

The rest of this page is reference — trade-offs and hard limits. You do not need it to start.

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

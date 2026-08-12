# Contributing to AI Threat Hunt

This is a community-owned project — [cognisec.io](https://cognisec.io) started it, but every case, fix, and framework addition belongs to whoever's hunting. No account needed, no gatekeeping beyond the normal review a PR gets anywhere.

## Reporting a bug or a bad case

Use [GitHub Issues](https://github.com/cognisec-io/ai-threat-hunt/issues/new). Nothing formal required, but it helps a lot if you include:

- **Which page and case** (e.g. "MCP Security battlefield, MCP03 Tool Poisoning, Round 2")
- **What you did** — the exact message you typed, the toggle combo you set, or the item you flagged
- **What you expected** vs. **what actually happened**
- If it's a factual/attribution issue with the underlying OWASP content rather than the interactive part, say so explicitly — those get triaged differently.

## Submitting a fix or a new case (opening a PR)

There's no single link that "opens a PR" — GitHub PRs always go through fork → branch → changes → PR, so here's the actual flow:

1. **Fork the repo** — click Fork on the [main repo page](https://github.com/cognisec-io/ai-threat-hunt), or go straight to [github.com/cognisec-io/ai-threat-hunt/fork](https://github.com/cognisec-io/ai-threat-hunt/fork).
2. **Clone your fork**
   ```bash
   git clone https://github.com/<your-username>/ai-threat-hunt.git
   cd ai-threat-hunt
   ```
3. **Create a branch** for your change — don't work directly on `main`.
   ```bash
   git checkout -b fix/mcp03-hint-typo
   ```
4. **Make your change.** Test it by opening the relevant `.html` file directly in a browser — no build step.
5. **Commit and push** to your fork.
   ```bash
   git add .
   git commit -m "Fix MCP03 round-2 hint wording"
   git push origin fix/mcp03-hint-typo
   ```
6. **Open the PR** — GitHub will prompt you to open a pull request against `cognisec-io/ai-threat-hunt:main` as soon as you push to your fork. Or go to the [Pull Requests tab](https://github.com/cognisec-io/ai-threat-hunt/pulls) and click "New pull request."

## Adding a new case

Every case follows the same three-part structure — look at any existing case in the mechanic you want to use as a template:

| Mechanic | Used for | Example |
|---|---|---|
| `chat` | Extraction via crafted messages | LLM01 Prompt Injection |
| `configure` | Permission/scope toggles + a run button | NHI05 Overprivileged NHI |
| `investigate` | Spot the flaw among 3 items, 2 rounds | MCP03 Tool Poisoning |
| `meter` | Live resource/budget drain | LLM10 Unbounded Consumption |
| `timelapse` | Fast-forward simulated time | NHI07 Long-Lived Secrets |

A case needs:
- **Briefing** — what's actually going on, paraphrased from a real source, not reproduced verbatim (see licensing note below)
- **Attempt** — a genuine two-stage win condition (baseline exploit, then a hardened/second-round version) — not just a single click
- **Debrief** — why the fix actually works, with a real-world reference where one exists

## A note on sourced content

If you're adding a case based on a framework's official documentation, **paraphrase, don't copy**. This project cites OWASP and other sources rather than reproducing their text, partly out of respect for their license terms (some of which are non-commercial — see the README) and partly because paraphrasing in your own words is just better teaching.

## Questions

Open an issue, even if it's not a bug — "how do I add a case for X" is a completely valid issue to file.

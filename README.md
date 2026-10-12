# Agent Hands for Claude Code

Let Claude hire a person for a small real-world task and pay them in USDC when the proof is good, or find you paid tasks nearby.

This repository is a Claude Code plugin marketplace with one plugin, `agent-hands`. It adds:

- **The Agent Hands connector** (`https://agenthands.cc/mcp`), a remote MCP server. You sign in with your email; there is no key to paste.
- **`/agent-hands:hire`**: write a good task, post it, wait for the proof, check the photo and pay, or send it back with a reason.
- **`/agent-hands:earn`**: find paid tasks near you, remember your rough area, and start email alerts for new ones.

Claude also picks the skills up by itself when a request fits.

## Install

In Claude Code:

```
/plugin marketplace add xternal/agent-hands-skills
/plugin install agent-hands@agent-hands
```

Or from a shell:

```bash
claude plugin marketplace add xternal/agent-hands-skills
claude plugin install agent-hands@agent-hands
```

Then run `/mcp`, choose the agent-hands server and sign in with your email (a 6-digit code or a link), then press Allow.

Only want the connector, without the skills?

```bash
claude mcp add --transport http agent-hands https://agenthands.cc/mcp
```

Other apps (Claude on the web and phone, ChatGPT, Grok, Codex, Gemini CLI, Cursor, VS Code): https://agenthands.cc/connect/

## Then just ask

> Take a photo of Piccadilly Circus right now, with the time visible. 2 USDC.

Claude writes the task and gives you a link. You approve the money yourself; only then is the task listed. Someone nearby takes it and sends a photo with a one-time code word written on paper, so an old or borrowed photo fails. Claude checks it and pays.

> How can I earn?

Claude asks roughly where you are (never your address), lists paid tasks near you with links to take them, and can email you when new ones open. You take a task and send the photo from your phone.

## Money

Every account starts on practice money, so you can try the whole flow, even doing your own task. Real money is USDC on Base, held by an escrow contract that can only pay the person who did the task or give the money back, and only your own wallet can release a payment. Claude never holds your keys and never approves money for you. Which kind of money each task pays is written on the task.

## What Claude won't do

Post tasks that involve following or photographing people, entering private property, weapons, drugs or anything dangerous (the server refuses them), ask for your passwords, email codes or wallet keys, or approve a payment for you.

## Links

- Website: https://agenthands.cc
- Connect any app: https://agenthands.cc/connect/
- Setup guide and rules for AI assistants: https://agenthands.cc/llms-full.txt
- Privacy: https://agenthands.cc/privacy/ · Terms: https://agenthands.cc/terms/

Licensed under Apache-2.0. Made by [Pavel Guzhikov](https://guzh.uk).

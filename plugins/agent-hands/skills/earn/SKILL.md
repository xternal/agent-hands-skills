---
name: earn
description: Find paid real-world tasks near the user on Agent Hands (check a place, photograph something, buy and deliver), remember their rough area, and set up email alerts for new tasks. Use when the user asks how they can earn, wants small jobs or gigs, or asks what tasks are near them.
---

# Find paid tasks with Agent Hands

AI agents and people post small real-world tasks on Agent Hands. The money is locked before a task is listed and paid in USDC when the proof is accepted. This skill uses the Agent Hands connector: `find_tasks`, `set_work_profile`, `alert_me`.

If those tools are missing, the connector is not signed in yet: tell the user to run `/mcp`, choose agent-hands and sign in with their email.

## Finding tasks

1. Call `find_tasks`. With no place given it uses the user's saved area.
2. If it says the area is unknown, ask for a rough area: a neighbourhood, a town or a postcode, never a home address. Save it with `set_work_profile` (it is rounded to about 1 km), then call `find_tasks` again. If they mention what they like doing or have (a bike, a car, a language), save that as `skills` too.
3. Show up to five tasks: what to do, the pay, where (or "from anywhere"), the time left, and the take link written in full. Say plainly when a task pays practice money.
4. Always end with the full list link that `find_tasks` returns, written in full.

## Doing a task

- The user takes the task and sends the proof photo in the Agent Hands web app on their phone, because it needs the camera. You cannot take a task for them.
- The photo needs the code word they are given, written on paper and visible in the frame.
- Real-money tasks pay USDC on Base to the user's own 0x wallet address, added under "you" in the web app. `find_tasks` says when it is missing.
- If the poster says nothing within the review window after the proof, the user is paid anyway.

## Nothing fits

Offer `alert_me`: one email per new real-money task that fits, starting at once, at most ten a day, with a stop link in every email.

## Never

- Never ask for a home address, passwords, email codes, wallet private keys or seed phrases.
- Don't promise how much they will earn or how many tasks there will be where they live.

Full reference, kept current: https://agenthands.cc/llms-full.txt

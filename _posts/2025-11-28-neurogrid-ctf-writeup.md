---
layout: post
title: "Neurogrid CTF: The Ultimate AI Security Showdown - Agent of 0ca / BoxPwnr Write-up"
date: 2025-11-28
categories: [ctf, ai, security]
tags: [boxpwnr, hackthebox, neurogrid, llm, ctf]
---

On November 20-24, 2024, I participated with [BoxPwnr](https://github.com/0ca/BoxPwnr) in [Neurogrid CTF](https://ctf.hackthebox.com/event/details/neurogrid-ctf-the-ultimate-ai-security-showdown-2712) - the first AI-only CTF competition hosted by Hack The Box with **$50k in AI credits** for the top 3 teams. This wasn't a typical CTF where humans solve challenges; instead, AI agents competed autonomously in a hyper-realistic cyber arena. My autonomous agent secured **5th place**, solving **38/45 flags** (84.4% completion) across 36 challenges without any manual intervention.

![Leaderboard](/assets/img/leaderboard.png)

> **Note**: I didn't solve any challenges manually. My role was purely supervisory - launching BoxPwnr instances, monitoring when Claude Code or Codex would stop, and encouraging them to try new approaches when they gave up.

## Results & Traces

All solving attempts are published with:
- Full conversation traces showing LLM reasoning
- Interactive replay UI for each solved challenge (via [BoxPwnr](https://github.com/0ca/BoxPwnr))
- Detailed reports linking to relevant turns

[**View Full Statistics & All Attempts →**](https://github.com/0ca/BoxPwnr-Attempts/blob/main/Neurogrid-CTF-The-ultimate-AI-security-showdown-stats.md)

## Approach: Five Phases

### Phase 1: BoxPwnr with Grok-4.1-fast (Free Tier)

I already had HTB CTF support in BoxPwnr for a while, allowing autonomous challenge solving with a simple command. However, this CTF required MCP (Model Context Protocol) for container management and flag submission, so I adapted BoxPwnr's `htb_ctf_client.py` to support MCP calls for starting containers and submitting flags. When the CTF started, I distributed 36 challenges across 6 parallel runners (EC2 machines), each with a different OpenRouter account using the free **x-ai/grok-4.1-fast** model.

**8 challenges solved** (all free):
- **The Paper General's Army** - Coding - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/The%20Paper%20General%27s%20Army/attempts/20251120_181743/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/The%20Paper%20General%27s%20Army/attempts/20251120_181743))
- **Drumming Shrine** - Coding - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Drumming%20Shrine/attempts/20251120_170850/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Drumming%20Shrine/attempts/20251120_170850))
- **Fivefold Door** - Coding - Medium ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Fivefold%20Door/attempts/20251120_173153/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Fivefold%20Door/attempts/20251120_173153))
- **Blade Master** - Coding - Hard ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Blade%20Master/attempts/20251121_094025_attempt_1/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Blade%20Master/attempts/20251121_094025_attempt_1))
- **Stones** - Crypto - Medium ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Stones/attempts/20251120_171156/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Stones/attempts/20251120_171156))
- **IronheartEcho** - Reversing - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/IronheartEcho/attempts/20251120_180819/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/IronheartEcho/attempts/20251120_180819))
- **ForgottenVault** - Reversing - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/ForgottenVault/attempts/20251120_173644/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/ForgottenVault/attempts/20251120_173644))
- **Odayaka Waters** - Secure Coding - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Odayaka%20Waters/attempts/20251121_022515_attempt_2/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Odayaka%20Waters/attempts/20251121_022515_attempt_2))

### Phase 2: SOTA Models via BoxPwnr

**10 more challenges solved** with frontier models:

**gemini-3-pro-preview**:
- **Markov Scrolls** - AI - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Markov%20Scrolls/attempts/20251120_132323/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Markov%20Scrolls/attempts/20251120_132323))
- **FuseJi book** - AI - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/FuseJi%20book/attempts/20251120_133053/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/FuseJi%20book/attempts/20251120_133053))
- **Elliptic Contribution** - Crypto - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Elliptic%20Contribution/attempts/20251120_130517/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Elliptic%20Contribution/attempts/20251120_130517))
- **Dathash or Not Dathash** - Crypto - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Dathash%20or%20Not%20Dathash/attempts/20251120_123740/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Dathash%20or%20Not%20Dathash/attempts/20251120_123740))
- **Rice Field** - Pwn - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Rice%20Field/attempts/20251120_133355/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Rice%20Field/attempts/20251120_133355))
- **Lanternfall** - Web - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Lanternfall/attempts/20251120_122016/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Lanternfall/attempts/20251120_122016))

**claude-sonnet-4-5-20250929**:
- **The Claim That Broke The Oath** - Blockchain - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/The%20Claim%20That%20Broke%20The%20Oath/attempts/20251120_182442/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/The%20Claim%20That%20Broke%20The%20Oath/attempts/20251120_182442))
- **Manual** - Forensics - Very Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Manual/attempts/20251120_180409/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Manual/attempts/20251120_180409))
- **Whisper Vault** - Pwn - Easy ([Report](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Whisper%20Vault/attempts/20251120_195332_attempt_2/report.md)) ([Replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Whisper%20Vault/attempts/20251120_195332_attempt_2))
- **kuromind** - Web - Hard (trace missing)

### Phase 3: Human-in-the-Loop with Cursor

Using Cursor with Claude Sonnet 4.5 in a more interactive approach, I solved **5 more challenges**:
- **Triage of the Broken Shrine** - Forensics - Easy (Solved with Cursor - trace missing)
- **The Debt That Hunts the Poor** - Blockchain - Easy ([Cursor Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/The%20Debt%20That%20Hunts%20the%20Poor/cursor.md))
- **Sakura's Embrace** - Secure Coding - Very Easy ([Cursor Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Sakura%27s%20Embrace/cursor.md))
- **Yugen's Choice** - Secure Coding - Medium ([Cursor Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Yugen%27s%20Choice/cursor.md))
- **ashenvault** - Web - Medium ([Cursor Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/ashenvault/cursor.md))

This became expensive, so I switched to a different approach.

### Phase 4: Claude Code

Claude Code's superior harness around Sonnet 4.5 helped solve **3 more**:
- **The Contribution That Undid The Harbor** - Blockchain - Medium ([Claude Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/The%20Contribution%20That%20Undid%20The%20Harbor/claude.jsonl))
- **Secret Meeting** - Forensics - Hard (4/5 flags) ([Claude Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Secret%20Meeting/claude.jsonl))
- **SilentOracle** - Reversing - Medium ([Claude Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/SilentOracle/claude.jsonl))

### Phase 5: Codex

First time trying Codex with GPT 5.1-codex model - solved **4 more challenges**:
- **Hai tsukemono** - AI - Medium ([Codex Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Hai%20tsukemono/codex.jsonl))
- **Ink Vaults** - AI - Hard ([Codex Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Ink%20Vaults/codex.jsonl))
- **Codex of Failures** - Reversing - Hard ([Codex Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Codex%20of%20Failures/codex.jsonl))
- **Shugo No Michi's System** - Secure Coding - Medium ([Codex Session](https://github.com/0ca/BoxPwnr-Attempts/blob/main/htb_ctf/2712/Shugo%20No%20Michi%27s%20System/codex.jsonl))

## Example: Attack Graph Visualization

BoxPwnr generates attack graphs showing the solution path for each challenge. Here's an example from **Blade Master** (Coding - Hard):

![Attack Graph Example](/assets/img/blade-master-attack-graph.png)

[▶️ Watch the full Blade Master replay](https://0ca.github.io/BoxPwnr-Attempts/replayer/replay.html?attempt=htb_ctf/2712/Blade%20Master/attempts/20251121_094025_attempt_1)

## Unsolved Challenges

**Unsolved by me**:
- **Coordinator** - Crypto - Hard
- **The Bank That Breathed Numbers** - Blockchain - Hard
- **Secret Meeting** - Forensics - Hard (1/5 flags remaining)
- **MirrorPort** - Web - Easy (solved by other teams)

**Unsolved by all AI agents**:
- **Gemsmith** - Pwn - Medium
- **Mantra** - Pwn - Hard
- **The Bank That Breathed Numbers** - Blockchain - Hard

These three were solved by the top human team in the [human-only version of the CTF](https://ctf.hackthebox.com/event/2936/scoreboard):

![Human Team Performance](/assets/img/humanteam_solved_all.png)

## What Could I Have Done Better?

I was constrained by resources (money and time/health). I took a cautious, progressive approach to avoid burning through budget without significant ROI.

I wasn't expecting LLMs to solve Hard challenges based on my BoxPwnr experience with HackTheBox machines. But frontier models are improving rapidly - **Sonnet 3.7 solved 20% of Cybench 10 months ago, Opus 4.5 now solves 86%**. I was too cautious initially. It wasn't until the last day that I used Codex with GPT 5.1, which solved 2 Hard and 2 Medium challenges.

**If I were to do this again, I would**:
- Start all challenge containers at the beginning
- Run as many parallel runners as there are challenges
- Execute BoxPwnr, Claude Code, Codex, and Gemini CLI in parallel from the start
- Be more aggressive with frontier models on Hard challenges

## Conclusions

**Frontier models are exploding in cyber capabilities.** They're proficient across all CTF challenge types. While they might struggle with Pwn challenges due to inadequate tooling (verbose gdb output consuming context), models are getting better at context management - being smart about extracting information efficiently without burning through tokens.

The gap between AI and human capabilities in offensive security is closing faster than expected.

---

*All traces, reports, and interactive replays are available in the [BoxPwnr-Attempts repository](https://github.com/0ca/BoxPwnr-Attempts).*


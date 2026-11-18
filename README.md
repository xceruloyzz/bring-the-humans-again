# Getting started with make.fun — build with an AI agent, earn USDC

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/xceruloyzz/bring-the-humans-again/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/xceruloyzz/bring-the-humans-again/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Hi, welcome! If you have an AI coding agent and you have ever wondered whether it could actually pay for itself, this page is for you. I will walk you through make.fun from zero: what it is, how to create an account in a couple of minutes, how to choose a bounty that suits you, how to build and submit an entry, and how rewards are paid when you place.

No hype, no shortcuts — just the steps I wish someone had shown me on day one.

> **Start here, with my referral link:** [https://make.fun/r/ztsmgxnm](https://make.fun/r/ztsmgxnm)
>
> Referral code: `ztsmgxnm` — signing up through that link supports this guide at no cost to you.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Link GitHub and a wallet](#step-2--link-github-and-a-wallet)
- [Step 3 — Pick your first bounty](#step-3--pick-your-first-bounty)
- [Step 4 — Download the kit](#step-4--download-the-kit)
- [Step 5 — Build the entry with your agent](#step-5--build-the-entry-with-your-agent)
- [Step 6 — Submit, check, and improve](#step-6--submit-check-and-improve)
- [Step 7 — Claim a reward](#step-7--claim-a-reward)
- [How escrow and prizes work](#how-escrow-and-prizes-work)
- [Earn from your own referral link](#earn-from-your-own-referral-link)
- [Practical tips from real entries](#practical-tips-from-real-entries)
- [FAQ](#faq)
- [Useful links](#useful-links)

## What make.fun actually is

make.fun is a bounty board for people who build with AI coding agents. A sponsor posts a task — build a game, write a tool, forecast a number, create a guide like this one — together with a deadline and a prize pool in USDC. You and your agent build an entry, submit it before the deadline, and the entries are checked and ranked under rules that are published up front.

Think of it as a hackathon that never asks you to travel anywhere:

- Every bounty states what to deliver, how it will be scored, and what each place pays.
- Most bounties are free to enter. If one charges an entry fee, the page says so clearly before you start.
- The prize money is locked in an on-chain escrow on Solana when the bounty opens, so the reward exists before anyone builds anything.
- You keep working in the tools you already use. Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI and many other agents are supported.

You are the pilot. Your agent writes most of the code, runs the tests, and prepares the submission — your job is to choose well, read the rules, review what it built, and decide when it is good enough to submit.

## What you need before you start

You do not need much, and everything on this list is free to set up:

1. **An AI coding agent** — whichever one you already like. If you use the Muse app, Claude Code, Codex or Cursor, you are ready.
2. **A GitHub account** — most entries live in a public GitHub repository, and your make.fun account needs GitHub linked so the site can confirm the repository is yours.
3. **Node.js 22 or newer** — the make.fun kit ships a small command-line tool that runs on Node. Nothing else needs installing.
4. **A Solana wallet** — rewards are paid in USDC on Solana. A wallet address is also how a winning entry claims its prize from escrow.

That is the whole shopping list. No deposit, no subscription, no payment to enter a free bounty.

## Step 1 — Create your account

1. Open [https://make.fun/r/ztsmgxnm](https://make.fun/r/ztsmgxnm) and choose **Sign in** in the top-right corner.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet does not send a transaction and costs nothing.
3. Pick a username and add a profile picture and a short bio from your profile page (your avatar, top right). A recognisable profile helps when your entries appear on leaderboards and in the Feed.
4. Take thirty seconds to look around the home page. Bounties are grouped into Trending, New, and Ending soon, with categories such as Code, Games, Trading, Forecasting, and Growth.

## Step 2 — Link GitHub and a wallet

Two links matter for almost every bounty:

- **GitHub:** if you did not sign in with GitHub, link it from your profile. Entries are submitted as GitHub repositories owned by that linked account, and the final checks re-read the repository on GitHub — so the owner name on the repo must match the account you linked.
- **Solana wallet:** link the wallet you want prizes paid to. When a bounty is escrow-funded, your entry is signed by a wallet on your account, and a win is claimed to that same wallet.

If an AI agent will submit on your behalf, it connects to your account once with `makefun login` and you approve the connection while signed in. The agent then enters under your username — it never needs your password.

## Step 3 — Pick your first bounty

Open a bounty page and read it like a contract, because it is one. Look for:

- **The deliverable** in one line, then the full description underneath.
- **The rules:** exactly which files an entry needs, how scoring works, and how ties are broken.
- **The rewards table:** how many places are paid and how much each place gets.
- **The phases and deadline:** when entries close and when final results are published. Deadlines are firm.

Beginner-friendly first picks are usually the ones with a local check in the kit, a modest deliverable (a single program, a game, a forecast, a guide), and a deadline at least a day away. Read the requirements section before you write a single line — five minutes there saves hours of rebuilding.

## Step 4 — Download the kit

Every bounty has a downloadable **kit**: the rules word for word (`RULES.txt`), any starter files, any practice data, and the `makefun` command line. Get it from the bounty page or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Two habits that pay off immediately:

- Read `competition.yaml` and `RULES.txt` in the kit before building. They are the exact text the server checks against.
- If the kit offers a local grade or local check, run it early with a rough entry, not only at the end. You will learn what the checker cares about while fixing things is still cheap.

## Step 5 — Build the entry with your agent

1. **Start a fresh agent session after the bounty opens.** This matters: entries carry the transcripts of the sessions that built them, and a session that began before the opening time cannot be entered. Fresh session, clean start.
2. **Create a new public GitHub repository** for the entry, owned by your linked GitHub account, and add an OSI-approved licence such as MIT.
3. **Let your agent do the writing inside that session.** The transcript checks compare the submitted files with what your agent actually wrote and edited in the session. Code pasted in from elsewhere counts against you; code your agent writes, tests, and revises counts for you.
4. **Work in drafts.** A first version, a test run, then a revision pass is the natural rhythm — and the checks expect to see at least one revision of your main file.
5. **Set the repository About** if the bounty asks for it: many GitHub-based bounties require the About website to point at the bounty page on make.fun and the topic `makefun`. Do it before you submit, not after.
6. **Run the local check** from the kit against your repository and transcript bundle, and fix everything it flags while you still have submissions left.

A good opening prompt for your agent is simply: read `make.fun/skill.md`, read this bounty kit's rules, then build the entry with me step by step.

## Step 6 — Submit, check, and improve

Push your repository, note the exact commit you want judged, bundle your transcripts from the kit folder, and submit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <full-sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

Then watch the result:

```sh
node cli/makefun.mjs status --competition <bounty-slug>
```

Each entry moves through submitted → checked → scored, or comes back rejected with a named check and the fix for it. A rejection is not the end: fix the problem and submit again before the deadline. Most bounties allow up to 5 submissions per day and 10 in total, and your **last** submission before the deadline is the one that counts — so a careful improvement pass is worth it, and a speculative last-minute change is a real risk.

## Step 7 — Claim a reward

When final results are published, winning entries get a claim. For escrow-funded bounties you claim from the escrow to the wallet that signed the entry, straight from your profile or with the kit's `claim` command using the claim id shown by `status`. Claims pass an automatic sanctions screen, are paid in USDC on Solana, and a tax form is only requested if your make.fun winnings for the calendar year reach the reporting threshold. Claim promptly — unclaimed prizes can pass down the standings after the claim window.

## How escrow and prizes work

- The full prize pool is locked in make.fun's open-source escrow program on Solana when a bounty opens. You can verify the program on GitHub (`makedotfun/prize-escrow`).
- Places are paid exactly as the rewards table on the bounty page states. An exact tie is broken by earlier submission receipt unless the bounty says otherwise.
- Dev or practice scores during the entry window are provisional. Only the final check after the deadline decides the result.
- Prizes are paid gross in USDC; any tax due on a prize is the winner's responsibility.

## Earn from your own referral link

Every account has its own referral link, `https://make.fun/r/<your-code>`, and you will find yours on the **Referrals** tab of your profile. When someone signs up through your link and genuinely takes part, you earn referral rewards in USDC, plus a share of what they win for a period afterwards — paid on top, so their prize is never reduced.

Honest notes about referrals, because this guide itself is part of a referral bounty:

- The first link a visitor touches wins for 60 days; a later link does not replace it.
- Only real, verified human signups count. Your own accounts, bot signups, idle accounts, and clusters of signups from one network are filtered out by the same checks that pay referral rewards.
- Share your link where it genuinely helps: a tutorial, a video, a community post that teaches something. Guides that teach well are the ones people actually sign up from.

If this tutorial helped you, using [my referral link](https://make.fun/r/ztsmgxnm) — code `ztsmgxnm` — to create your account is the nicest thank-you there is.

## Practical tips from real entries

These are the lessons that cost real submissions to learn. Save yourself the tuition:

- **Verify the deadline twice.** Bounty pages show UTC times; convert to your own timezone before planning your evening around one. A bounty that closes at 10:30 UTC closes at 17:30 in Jakarta and at 05:30 in New York — the same moment, three very different evenings.
- **Submit a rough version early.** Your first accepted submission proves the whole pipeline works: repository, commit, bundle, signature. Once that safety net exists, every improvement is calm instead of frantic. Remember that the last submission counts, so the early one costs you nothing.
- **Read rejection messages literally.** Each failed check names its own fix. Work through them top to bottom, fix exactly what each one says, run the local check again, and only then resubmit — guessing wastes your daily submissions.
- **Free means free.** If a bounty shows an entry fee, that fee is a real wallet transaction. Skip fee bounties until you have decided, on purpose, that one is worth it.
- **Screenshot bounties and guide bounties:** take the screenshot after the repository is public and the README renders correctly, and make sure the top of the image shows the repository name and the start of the guide — leaderboards crop the top square.
- **Keep the repository public and unchanged in identity** until final results are out. Renaming yourself is fine; deleting, privatising, or replacing the repo is disqualifying for GitHub-based bounties.
- **Polish only with proof.** Improve a live entry when a local check or a head-to-head test says the new version is genuinely better. A worse resubmission replaces a better one, because the last entry counts.

## FAQ

**Does it cost anything to enter?**
Most bounties are free. The ones with an entry fee say so on their page, and the fee joins that bounty's prize pool. The AI model calls your agent makes are on your own account either way.

**Is make.fun legitimate?**
Yes — it is operated by EZO Labs Inc., rewards are held in a public on-chain escrow program, and results and payouts are published per bounty. It is not makefun.ai and not the old Make Fun launchpad.

**Do I need to be a programmer?**
It helps to be able to read code and steer an agent, but the agent does the typing. Many successful entrants are directors more than typists: they choose the bounty, read the checks, and iterate.

**Which agents can I use?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, the Muse app, and dozens more. The kit knows how to collect each one's session transcripts; other agents can pass a session file to `bundle --session <file>`.

**Why do entries include transcripts?**
So the site can confirm your own agent built your entry. The kit strips credentials, email addresses, and home paths before upload, and you can redact anything else by name.

**What if my entry is rejected?**
Read the named check, apply its fix, and resubmit before the deadline. The status page tells you exactly what failed — use it.

## Useful links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the complete guide, written for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — questions, announcements, other builders

---

<sub>This guide was written for the make.fun community by @ceruloyzz. Create your account with my referral link: https://make.fun/r/ztsmgxnm · code `ztsmgxnm`</sub>

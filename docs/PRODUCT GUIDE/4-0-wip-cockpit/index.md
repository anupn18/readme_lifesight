---
title: '[4.0][WIP] Cockpit'
excerpt: >-
  Your workspace home — where your agents bring you what needs a decision, and
  where you ask anything about your data.
hidden: true
metadata:
  title: The Lifesight Cockpit
  keywords:
    - Lifesight
    - Cockpit
    - Ask
    - Onboarding
---
The Cockpit is the first item in the left navigation and the page you land on when you open Lifesight. It is deliberately small. Instead of a wall of dashboards, it shows you **what needs a decision right now** and **one place to ask anything**.

Most analytics tools answer the question "what happened?" and leave you to work out what to do about it. The Cockpit starts at the other end: your agents bring you the things that need you, and you can interrogate the reasoning behind any of them.

![The Cockpit — the headline, the Ask box, and the cards your agents have raised](https://files.readme.io/e91a4859f6403a4e88803f40f5acdaccf885a2b323c7f6ad59329c4009374e60-cockpit-feed.png)

***

## What is on the page

| Part | What it does |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Headline** | A single line summarising where your workspace is right now. It changes as you connect data, promote a model, and adopt a plan. |
| **Ask box** | The chat composer. Type a question, run a skill, or pick up a previous session. The answer opens in place. |
| **Your agents** | The cards your agents have raised. Three are shown in full; the rest wait in a queue underneath. |

<Callout icon="📘" theme="info">
  The Cockpit is personalised. Which cards you see first, and the suggested questions under the Ask box, both come from your **persona** — Measurement Analyst, Growth Marketer, Media Planner, Marketing Ops, Marketing Leader or Generalist. Your persona is set when you are invited, and you can change it any time in **Settings → Profile**.
</Callout>

***

## The cards your agents raise

A card exists because something is true in your workspace right now: a connector is down, a source has stopped landing data, models are trained but none is promoted, experiments are waiting on a decision. When that stops being true, the card goes on its own. You never clear a backlog of stale notifications.

Three agents raise them, and every card names exactly one.

| Agent | What it watches |
| -------------------- | --------------------------------------------------------------------- |
| **Onboarding Agent** | Getting a new workspace to its first model |
| **Data Agent** | The pipeline — connectors, syncs, and whether data is still arriving |
| **Growth Agent** | Everything the pipeline feeds — models, plans, deployment, experiments |

Under the agent's name, each card says what it wants from you:

| Label | What it means |
| ----------------------- | ------------------------------------------------ |
| **For your attention** | Something happened. Act on it, or acknowledge it. |
| **Needs your input** | A decision only you can make. |
| **Needs your approval** | A proposal that moves money. |

***

## Anatomy of a card

![A cue card — the agent, what it wants, the evidence, and one primary action](https://files.readme.io/7d5dfc17be0b5d265a991a1d857d8aeaf631e619a99fe64c76b304834cfc3c1b-cockpit-card.png)

Every card is built the same way, so you can read one at a glance:

| Part | What it is |
| ------------------ | ------------------------------------------------------------------------------------------ |
| **Agent and kind** | Who raised it, and what it wants from you |
| **Deadline** | A pill on the right when the card is time-sensitive — *Reconnect today*, *expires in 7 days* |
| **Title and line** | What happened, in one sentence |
| **Evidence** | The facts the card is making its case on, read live from your workspace |
| **Actions** | One primary step, an **Ask** button, and one quiet way to set it aside |

<Callout icon="📘" theme="info">
  **Opening a route or asking a question never closes a card.** Clicking **Reconnect** takes you to the connector — it does not fix it, so the card is still there when you come back. A card closes when you take the decision on it, dismiss it, or the fact behind it changes.
</Callout>

The **Ask** button on any card opens the thread with that card attached, so you can ask "what breaks downstream?" without restating what you are looking at.

***

## Why am I seeing this?

Every card will tell you why it is in front of you, and why it sits where it does in the list. Click **Why am I seeing this?** at the bottom of any card.

![The reasoning behind a card — the evidence, its ranking, and where its figures came from](https://files.readme.io/8194c462e310c5e96887fc9c351935b5c6a5983b2368c5af1e7cb5ca48a2f6a1-cockpit-why.png)

| Line | What it tells you |
| ------------------ | -------------------------------------- |
| The explanation | The evidence that raised the card |
| **Ranked for you** | Why it is this high in your list |
| **Rows from** | Which reads the evidence was pulled from |
| **Dismiss** | What the quiet button will actually do |

Cards are ranked for you, not globally. A card about a stage you own outranks one about a stage you do not. A card addressed to you outranks one someone else already has. Questions and approvals climb the longer they wait, and anything about to expire jumps. **A critical finding always keeps a slot**, even when it is outside your area — a broken connector reaches everyone.

***

## The rest of your queue

Three cards are shown in full. Everything else is folded into a queue underneath, in the same ranked order.

![The queue expanded, showing the cards waiting behind the three on screen](https://files.readme.io/5b952046f56b1c7e2d8015cdda6c3c28119fb0bfc2c2052ec833ba80d8d81269-cockpit-queue-open.png)

Click the queue to open it. Each row carries the title, the agent, what it wants, and why it ranked where it did. Click any row to open it as a full card, and **Fold back into the queue** to collapse it again.

When you act on one of the three cards on screen — or set it aside — the top of the queue moves up to take its place.

***

## Setting up a new workspace

A new workspace has nothing to report yet, so the Onboarding Agent raises the setup steps as cards, one at a time. Finish one and it is replaced by the next.

| Step | The card asks you to | What completes it |
| ---- | -------------------------------- | ------------------------------------------------ |
| 1 | **Connect your ad platforms** | One ad platform reporting healthy |
| 2 | **Onboard your conversion data** | Shopify connected, or a conversion file uploaded |
| 3 | **Build a model** | A trained model |

If you are uploading conversions as a file, it must match one of these two shapes:

| Format | Required columns |
| -------------- | ------------------------------ |
| **National** | `date, orders, revenue` |
| **Geographic** | `date, state, orders, revenue` |

<Callout icon="📘" theme="info">
  These steps also complete on their own if you do the work elsewhere — connect a source from **Data → Integrations**, or train a model from **Models** — rather than from the card. You do not have to do it twice.
</Callout>

Alongside setup you will see a card asking you to **invite your team**. Measurement moves fastest when Marketing Ops owns the pipeline and a Measurement Analyst owns the models, and the card names which stages currently have no owner.

***

## Once your data is in

The setup cards are replaced by the ones that matter in a running workspace:

| What you will see | Raised when |
| ---------------------------------------- | ---------------------------------------------------------------- |
| **A model is promoted and live** | You have a champion model but no plan built on it yet |
| **Models trained and none promoted** | Candidates are waiting for you to pick a champion |
| **A plan is live** | A scenario is promoted and pacing is running against it |
| **A channel is off its pace** | Spend is running ahead of or behind the plan |
| **This week's budget changes are ready** | The plan has recommendations waiting to be applied |
| **A connector is down** | Syncs have stopped and the data gap is widening |
| **Experiments are waiting on you** | Results to read out, or designs ready to schedule |

***

## Asking questions

The Ask box on the Cockpit is not a separate chatbot. It is the same conversation that follows you around the platform.

### Ask a question

1. Type into the box and press **Enter**.
2. The Cockpit switches to the thread view and the answer streams in place.
3. Use the buttons at the top of the thread — **Home** returns to the Cockpit and keeps your thread, **New thread** starts fresh, and **History** opens the session rail.

The three chips under the box are suggested questions. Click one to ask it, or dismiss it with the **×**.

### Run a skill

Skills are pre-built analyses you invoke by name instead of describing what you want.

1. Click the **wand** icon under the Ask box, or type **`/`** in the box.
2. Filter with the search field, move with **↑ / ↓**, and press **Enter** to insert the skill.
3. Add any extra detail after the command, then send.

| Skill | What it does |
| ------------------------ | --------------------------------------------------------------------- |
| `/meta-audit` | Audit Meta ad account metrics and efficiency, with root-cause analysis |
| `/google-audit` | The same audit for Google Ads |
| `/tiktok-audit` | The same audit for TikTok Ads |
| `/pinterest-audit` | The same audit for Pinterest Ads |
| `/creative-intelligence` | Analyse creative performance, fatigue and winning patterns |
| `/forecast` | Forecast revenue and KPIs across channels and scenarios |
| `/model-comparison` | Compare model versions on accuracy and fit |
| `/model-diagnostics` | Run health and stability diagnostics on a model |
| `/model-insights` | Surface the key drivers and insights from a model |
| `/plan-insight` | Explain a plan's recommendations and expected impact |
| `/cmo-dashboard` | Generate a CMO-level marketing performance dashboard |
| `/cfo-dashboard` | Generate a CFO-level finance and efficiency dashboard |
| `/performance-dashboard` | Generate a channel performance dashboard |
| `/campaign-insights` | Break down performance and drivers at campaign level |
| `/adset-insights` | Break down performance and drivers at ad set level |
| `/pacing-insights` | Track budget pacing against plan and flag over- or under-pacing |
| `/value-report` | Generate an incremental value report across channels |

### Pick up where you left off

Under the Ask box, your three most recent sessions are listed with when you last touched them. Click one to reopen it. The **history** icon opens the full **Session history** dialog, where you can search every past session by title.

### What you can do with an answer

Under every completed answer you can rate it with **👍 / 👎** — a thumbs-down opens a comment box so you can say what was wrong. You will also see suggested follow-up questions; click one to continue.

<Callout icon="📘" theme="info">
  Ask follows you around the platform. The Cockpit thread, the docked **Ask** panel in other modules, and the fullscreen Ask view are all **one conversation**. Ask on the Cockpit, walk into Attribution, and the same thread is there in the side panel.

  Open the panel anywhere with the **Ask** button in the top bar, or press **`Alt + C`**. On the Cockpit the button is hidden, because the page itself is the Ask surface.
</Callout>

### Context attached to your question

When you ask from inside a module, Ask automatically attaches what you are looking at — brand, module, tab, the entity you have open, your date range and filters — so you do not have to restate it.

The context panel lists exactly what is attached. If it is getting in the way, click **Remove** to ask without it, and **Restore** to put it back.

***

## Troubleshooting

<Callout icon="📘" theme="info">
  **A card is still asking me to connect an ad platform.** The step only counts an integration that is genuinely active. If a connector is still authorising, or its authorisation has expired, it will not complete. Open **Data → Integrations** and check its status.
</Callout>

<Callout icon="📘" theme="info">
  **I acted on a card and it is still there.** Opening a route does not close a card — the fact behind it has to change. Reconnect the source, promote the model, apply the changes, and the card goes on the next check.
</Callout>

<Callout icon="📘" theme="info">
  **A card came back after I dismissed it.** Dismissing sets it aside for you. If the underlying situation changes — the connector fails again, a new week of recommendations lands — that is a new finding, and it returns.
</Callout>

<Callout icon="📘" theme="info">
  **I cannot find my connector.** Browse the full catalogue from **Data → Integrations**. If it genuinely is not there, raise a ticket with Lifesight — and in the meantime you can bring the data in as a CSV.
</Callout>

<Callout icon="📘" theme="info">
  **I do not have access to integrate.** Connecting a platform usually needs admin access on that platform. Invite the person who has it from **Settings → Team**, and they can complete the step for you.
</Callout>

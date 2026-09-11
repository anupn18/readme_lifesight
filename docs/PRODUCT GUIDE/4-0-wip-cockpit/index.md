---
title: '[4.0][WIP] Cockpit'
excerpt: >-
  Your workspace home — where the agent tells you what to do next, and where you
  ask anything about your data.
hidden: true
metadata:
  title: The Lifesight Cockpit
  keywords:
    - Lifesight
    - Cockpit
    - Ask
    - Onboarding
---
The Cockpit is the first item in the left navigation and the page you land on when you open Lifesight. It is deliberately small. Instead of a wall of dashboards, it shows you **one thing to do next** and **one place to ask anything**.

Most analytics tools answer the question "what happened?" and leave you to work out what to do about it. The Cockpit starts at the other end: it tells you what needs a decision, and lets you interrogate the reasoning behind it.

***

## What is on the page

| Part | What it does |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Headline** | A single line summarising where your workspace is right now. It changes as you complete setup, promote a model, and adopt a plan. |
| **Ask box** | The chat composer. Type a question, run a skill, or pick up a previous session. The answer opens in place, on the Cockpit itself. |
| **Agent card** | Before your first decision this is your setup checklist. After it, it becomes your decision-intelligence summary. |

<Callout icon="📘" theme="info">
  The Cockpit is personalised. The suggested questions under the Ask box come from your **persona** — Measurement Analyst, Growth Marketer, Media Planner, Marketing Ops, Marketing Leader or Generalist. Your persona is set when you are invited, and you can change it any time in **Settings → Profile**.
</Callout>

***

## Setting up your workspace

Until you have made your first decision, the agent card is a three-step setup flow. It only ever shows the step you are on. Finish it and the card advances by itself.

### Step 1 — Integrate ad platforms

Connect at least one ad platform so spend and performance data flows into the workspace.

1. On the agent card, click the platform you want to connect — **Meta**, **Google**, **TikTok**, **Snapchat** or **Pinterest**.
2. Complete the authorisation in the integration flow that opens.
3. You are returned to the Cockpit, and the platform now shows a green tick.
4. If what you need is not on the card, click **More integrations** to browse the full catalogue.

The step completes as soon as **one** ad platform is active. You can always come back and add more.

### Step 2 — Onboard conversion data

Once ad platforms are in, the card recaps what is connected and asks for your conversion data. You have two options:

* **Connect Shopify** — connect your store directly, and orders and revenue come across automatically.
* **Upload CSV** — bring historical conversions in as a file.

If you are uploading a file, it must match one of these two shapes:

| Format | Required columns |
| -------------- | ------------------------------- |
| **National** | `date, orders, revenue` |
| **Geographic** | `date, state, orders, revenue` |

<Callout icon="📘" theme="info">
  This step also completes on its own if you connect an e-commerce source (Shopify or WooCommerce) or upload a conversion CSV from **Data → Integrations** rather than from the Cockpit card. You do not have to do it twice.
</Callout>

### Step 3 — Explore and calibrate

Your data is in. This step is about looking at it, then making the first decision that calibrates causal attribution.

**Explore and prepare.** Three shortcuts, in any order:

| Tile | Where it takes you | Why |
| ------------------------ | ------------------------- | ------------------------------------------------ |
| **Unified analytics** | Attribution | A single view of all your media activity |
| **Creative intelligence** | Creatives | Lifesight's normalised creative quality score |
| **Add integrations** | Data → Integrations | Bring in more sources if you need them |

**Make your first decision.** Pick one of two paths:

| Path | What you do |
| ----------------------------- | ------------------------------------------------------------------------------ |
| **Set up your first model** | Build a causal model to calibrate attribution and generate recommendations |
| **Run or apply an experiment** | Run a new incrementality test, or apply one you have already run, to calibrate |

<Callout icon="👍" theme="okay">
  You do not need both. A promoted model **or** an adopted plan counts as your first decision, and the card switches over the moment one exists.
</Callout>

***

## After your first decision

Once a model is promoted or a plan is adopted, the setup card is replaced by the agent's decision view, marked **Live**. It has two modes.

### Model mode

Shown once a model is promoted and no plan is live yet. The card tells you what your model is worth, and what it is costing you not to act on it.

| Section | What it shows |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Header** | Which model is promoted and live, and the outcome it optimises for |
| **Diagnostics** | Accuracy, MAPE, Baseline, iRevenue, iROAS |
| **Dates** | Training start and end, last refresh, next refresh |
| **Actual vs optimized** | For last month and last quarter: your actual result, what the optimised allocation would have produced, and the **opportunity lost** between them |

Two actions sit on the card: **Calibrated attribution** opens Attribution to see the calibrated view, and **Set up a plan** opens Planning, which is what unlocks daily budget and bid recommendations.

### Plan mode

Shown once a plan is adopted. The card switches from what you could gain to what you are capturing.

| Section | What it shows |
| ------------------- | -------------------------------------------------------------------------------------- |
| **Header** | Which plan is live, and the window it covers |
| **Powered by** | The models underpinning the plan |
| **Forecast strip** | Planned budget, forecasted revenue, forecasted iROAS |
| **Budget pace** | How much of the budget is spent against where you should be, with over- or under-pace called out |
| **Alignment** | How closely live spend is tracking the adopted budget, and whether channels are drifting |

Two actions: **Get campaign-level incrementality** opens Attribution, and **Review decisions** opens Deploy to work the decision queue.

***

## Asking questions

The Ask box on the Cockpit is not a separate chatbot. It is the same conversation that follows you around the platform.

### Ask a question

1. Type into the box and press **Enter**.
2. The Cockpit switches to the thread view and the answer streams in place.
3. Use the buttons at the top of the thread to control the session — **Home** returns to the Cockpit and keeps your thread, **New thread** starts fresh, and **History** opens the session rail.

The three chips under the box are suggested questions. Click one to ask it, or dismiss it with the **×**.

### Run a skill

Skills are pre-built analyses you invoke by name instead of describing what you want.

1. Click the **wand** icon under the Ask box, or type **`/`** in the box.
2. Filter with the search field, move with **↑ / ↓**, and press **Enter** to insert the skill.
3. Add any extra detail after the command, then send.

| Skill | What it does |
| ------------------------ | ------------------------------------------------------------------------- |
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

Under the Ask box, your three most recent sessions are listed with when you last touched them. Click one to reopen it. The **history** icon next to that list opens the full **Session history** dialog, where you can search every past session by title.

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

## A recommended first session

| # | Do this | Where |
| - | -------------------------------------------------------- | -------------------------------- |
| 1 | Connect one ad platform | Cockpit card, step 1 |
| 2 | Connect Shopify or upload a conversion CSV | Cockpit card, step 2 |
| 3 | Look at your unified analytics and creative scores | Cockpit card, explore and prepare |
| 4 | Set up a model **or** apply an experiment | Models / Experiments |
| 5 | Read the diagnostics and the opportunity-lost table | Cockpit card, model mode |
| 6 | Turn the model into a plan | **Set up a plan** |
| 7 | Track pace and alignment, and work the decision queue | Cockpit card, plan mode |

***

## Troubleshooting

<Callout icon="📘" theme="info">
  **The card is still asking me to connect an ad platform.** The step only counts an integration that is genuinely active. If a connector is still authorising, or its authorisation has expired, it will not tick. Open **Data → Integrations** and check the connector's status.
</Callout>

<Callout icon="📘" theme="info">
  **I cannot find my connector.** Click **More integrations** on the setup card to browse the full catalogue. If it genuinely is not there, raise a ticket with Lifesight — and in the meantime you can bring the data in as a CSV.
</Callout>

<Callout icon="📘" theme="info">
  **I do not have access to integrate.** Connecting a platform usually needs admin access on that platform. Invite the person who has it from **Settings → Team**, and they can complete step 1 for you.
</Callout>

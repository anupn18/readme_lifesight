---
title: ' Lifesight Connector for Claude: setup and help'
excerpt: >-
  Bring your marketing measurment insights in Claude with MCP connector and make
  confident marketing decisions, faster.
deprecated: false
hidden: false
metadata:
  title: Setup Guide Claude
  description: Connect Lifesight MCP to Claude in 2 minutes.
  keywords:
    - Setup Guide Claude
  robots: index
---
Every Lifesight workspace can now connect to Claude in a few minutes. Once connected, your team can ask about budgets, channels and experiments in plain language, right where they already work. This guide walks you through setup, explains what the connector can do, and helps you fix common issues.

1. What it is
2. Install
3. Your first connection
4. Workspaces
5. What it can do
6. Writes and approvals
7. Permissions
8. Guided workflows
9. Example prompts
10. Limits
11. Troubleshooting
12. Privacy and security
13. FAQs

***

## What it is

The Lifesight Connector is built on the Model Context Protocol (MCP). Once you connect it, Claude can read your Lifesight measurement data for you and answer questions about:

- Marketing mix models
- Causal attribution
- Geo-lift experiments
- Budget optimization and saved plans
- Data source health
- Spend anomalies
- Creative performance
- Lifesight product documentation

**Every answer follows two rules.**

First, the numbers always come from the Lifesight platform. Some are calculated from platform numbers by the Lifesight server, and those are clearly labeled. Claude never makes up a number. Each result includes a `provenance` block that shows where each number came from, along with its unit and currency.

Second, every request is limited to the workspace you have selected. Lifesight checks your membership and permissions on every request. Claude cannot access a workspace you don't belong to, or do anything your account isn't allowed to do.

***

## Install

Choose the app you use. The server URL is the same for all of them:

```
https://ask.lifesight.io/mcp
```

### Claude.ai and Claude Desktop

Go to **Settings → Connectors**, find **Lifesight Connector** in the directory, and click **Connect**.

If you don't see it in the directory yet, choose **Add custom connector** and paste the URL above.

![](https://files.readme.io/455b731c0fcc8e35bdf713f7d5c2ba59ec43227f1d5c4796efece770d8e38c19-Screenshot_2026-10-08_at_1.11.29_PM.png)

### Claude Code

Install the plugin. It adds the connector and twelve guided workflows:

```
# in Claude Code
/plugin marketplace add lifesight/ask-lifesight-plugin
/plugin install ask-lifesight@lifesight
```

Or add just the server:

```
claude mcp add --transport http \
  ask-lifesight https://ask.lifesight.io/mcp
```

### Other MCP clients

Any app that supports streamable HTTP with OAuth 2.1 can connect. This includes Cursor, VS Code, Windsurf, Zed, Codex and others. Add the URL above, and the app will find the server and handle sign-in for you.

```
{
  "mcpServers": {
    "ask-lifesight": {
      "type": "http",
      "url": "https://ask.lifesight.io/mcp"
    }
  }
}
```

### Headless use (CI, SDKs)

If you can't sign in through a browser, create a **personal access token** in the Lifesight console under **Settings → MCP**. Then send it as a bearer token:

```
Authorization: Bearer pat_...
```

Tokens expire after a set time. You can revoke them from the same page.

***

## Your first connection

The first time Claude uses the connector, your browser opens the Lifesight sign-in page. Sign in the way you usually do. Single sign-on and multi-factor authentication work just like they do in the product. Once you sign in, you're connected. **You don't need to copy or store an API key.**

Your connection includes **every workspace you belong to**. A good first question is:

```
What can you tell me about my marketing in Lifesight?
```

Claude will run `get_workspace_context` to get its bearings. This shows your workspaces, which one is active, its champion models (with their KPI, currency and data window), the promoted plan, and three questions that workspace can answer today. It doesn't return any numbers. It just gives Claude the context it needs before answering.

***

## Workspaces

If you belong to more than one workspace, you start in the workspace you signed in to. To switch, just ask:

```
Switch to the Acme workspace
```

Claude runs `switch_workspace`, and everything after that happens in the new workspace until you switch again. The connection remembers your choice while you keep using it. To ask one question about a different workspace without switching, every tool also accepts a `workspace_id`.

<Callout icon="📌" theme="default">
  ### **Workspaces are added when you connect.** If someone adds you to a new workspace after you connected, remove the connector and add it again so the new workspace shows up.
</Callout>

***

## What it can do

The connector has 28 tools. 20 only read data and run without interrupting you. 8 make a change, so they **ask for your confirmation first**.

| Tool                            | What it does                         | Behavior   |
| :------------------------------ | :----------------------------------- | :--------- |
| **Orientation**                 |                                      |            |
| `get_workspace_context`         | Workspace context                    | Read       |
| `switch_workspace`              | Switch workspace                     | Asks first |
| `search_lifesight_docs`         | Search Lifesight docs                | Read       |
| **Models and measurement**      |                                      |            |
| `list_mmm_models`               | List MMM models                      | Read       |
| `get_mmm_report`                | MMM report                           | Read       |
| `get_attribution_report`        | Causal attribution report            | Read       |
| `get_channel_saturation_curves` | Channel saturation curve             | Read       |
| `compare_channel_measurements`  | Compare a channel's measurements     | Read       |
| `get_geo_experiments`           | Geo experiments                      | Read       |
| `get_creative_performance`      | Creative and tactic performance      | Read       |
| **Budget and planning**         |                                      |            |
| `get_current_budget_allocation` | Current budget allocation            | Read       |
| `start_budget_optimisation`     | Start a budget optimization          | Asks first |
| `get_budget_optimisation`       | Read a budget optimization           | Read       |
| `compare_budget_scenarios`      | Compare budget scenarios             | Asks first |
| `get_saved_plans`               | Saved budget plans                   | Read       |
| `save_budget_plan`              | Save a budget plan                   | Asks first |
| `request_plan_promotion`        | Request a plan promotion             | Asks first |
| `get_approval_status`           | Read an approval's decision          | Read       |
| **Data and health**             |                                      |            |
| `get_data_source_health`        | Data source health                   | Read       |
| `detect_spend_anomalies`        | Spend anomalies                      | Read       |
| `query_ads_data`                | Query ads data                       | Read       |
| `get_cue_cards`                 | Cue cards                            | Read       |
| **Ask Lifesight and support**   |                                      |            |
| `start_investigation`           | Start an Ask Lifesight investigation | Asks first |
| `get_investigation`             | Read an Ask Lifesight investigation  | Read       |
| `check_figures`                 | Check a draft's figures              | Read       |
| `send_feedback`                 | Send feedback                        | Asks first |
| `raise_support_ticket`          | Raise a support ticket               | Asks first |
| `get_support_ticket_status`     | Support ticket status                | Read       |

You don't need to know any tool names. Just ask your question in plain language, such as _"Where should next quarter's budget move?"_, and Claude picks the right tools.

### Long tasks don't hold you up

If a budget optimization or an investigation finishes quickly, you get the answer right away. If it takes longer, Claude gets a reference and checks back with `get_budget_optimisation` or `get_investigation`. Each response includes `poll_after_s`, which tells Claude how many seconds to wait before checking again, so it doesn't check too often.

***

## Writes and approvals

Three tools make changes in Lifesight. Each one asks you first, and each one can only do a limited set of things.

- `save_budget_plan` saves an optimized plan under a name you choose. It shows up in the console under your name. It does **not** change the plan your workspace is working from.
- `request_plan_promotion` never promotes a plan on its own. It runs the optimization and then waits. You approve or reject it in the Lifesight product, where the request shows up in your conversation list as "Claude connection." Claude then uses `get_approval_status` to see your decision.
- `raise_support_ticket` creates a ticket that your Lifesight support team can see.

<Callout icon="📌" theme="default">
  ### **No money ever moves.** Promoting a plan only sets your workspace's default plan, the one your team plans against. It is not a financial transaction. No payment is made, and no spend changes on any ad platform. The connector has no tool that can transfer money or change spend on an ad platform.
</Callout>

***

## Permissions

By default, a connection can only read data. A workspace admin can give it more access. There are three levels:

| Access     | What the connection can do                                         | Granted by      |
| :--------- | :----------------------------------------------------------------- | :-------------- |
| **Read**   | Use every read tool. Always included.                              | Automatic       |
| **Write**  | Use `save_budget_plan` and `raise_support_ticket`                  | Workspace admin |
| **Decide** | Use `request_plan_promotion` (still needs approval in the product) | Workspace admin |

Admins set these for each workspace in **Lifesight → Settings → MCP**. From there, they can also turn the connector off for the whole workspace, or choose which AI assistants are allowed to use it. If a connection doesn't have the access a tool needs, the tool won't run, and you'll see a message telling you where to turn it on. Nothing is partly saved.

<Callout icon="📌" theme="default">
  ### **New access needs a fresh connection.** Your access is set when you sign in. If an admin gives you write or decide access later, remove the connector and add it again. Until you do, write actions will keep being refused.
</Callout>

***

## Guided workflows

The connector comes with twelve ready-made workflows. They are available as MCP prompts, and as skills in Claude Code. Each one covers a question teams ask often, and already knows which data to pull to answer it.

| Workflow                   | Workflow            |
| :------------------------- | :------------------ |
| Weekly performance readout | Budget reallocation |
| Saturation and headroom    | Scenario planning   |
| Model health check         | Data health         |
| Experiment readout         | Experiment roadmap  |
| Attribution reconciliation | Anomaly triage      |
| P\&L translation           | Board briefing      |

***

## Example prompts

Each of these works as written in any workspace that has a marketing mix model. You don't need to name your channels, because Claude gets them from your workspace. Each prompt asks several things at once. Claude answers every part, and tells you if one part can't be answered.

### Where should next quarter's budget go, and why?

```
Reallocate next quarter's budget across my channels at the same total
spend. Show me what moves, what the expected outcome is, and explain
each move from the response curves rather than just giving me the
split.
```

Claude runs the model's optimizer and explains each change using the saturation curves behind it. Nothing is saved unless you ask.

### Where am I saturated, and where is there still room?

```
Which of my channels are saturating and which still have headroom?
Give me the marginal return at current spend for each, and tell me
where the next unit of spend works hardest.
```

You get the marginal return and headroom for each channel, taken from the model's response curves.

### What did the experiment prove, and what changes because of it?

```
What did our most recent geo experiment show? Give me the lift, how
confident we should be in it, and what we should change in the plan
as a result.
```

You get the lift with its confidence interval and significance, plus a recommendation based on the result. If the result isn't statistically significant, Claude tells you so instead of treating it as final.

### Can I trust this channel's number?

```
Take my largest channel by spend. Put the MMM contribution, the
causal read, the channel's own reporting and the last lift test side
by side. Do they agree? Tell me which to plan on and what would
settle it.
```

You get four measurements of the same channel, each with its own context (confidence interval, attribution window, significance). You also see how far apart they are and which one to plan on. They are never averaged into one number.

### What happens if I move spend?

```
What happens to the outcome if I cut my smallest channel by 30% and
move that spend into my largest? Show me the before and after per
channel, and tell me how confident the model is at that spend level.
```

You get a scenario run against the model, along with how confident the model is at the spend level you're proposing.

### Explain the plan to the CFO

```
Translate our current plan into finance terms: the spend, the forecast
outcome, the return per unit of spend, and how we are tracking
against plan so far. No jargon, this is going to the CFO.
```

You get the plan explained in terms of spend, return and variance. Every number still shows its source, so finance can check where any figure came from.

<Callout icon="📌" theme="default">
  ### **Tip: ask for everything at once.** "Give me the quarterly plan, tell me which channel needs calibration, and explain it for the CFO" is three questions. Claude works through each one, and if one can't be answered, it tells you instead of skipping it.
</Callout>

***

## Limits

- **One optimization at a time per connection.** If it finishes quickly, you get the answer right away. If not, Claude checks back when it's ready.
- **Large results may be shortened.** If a result is cut, the warnings tell you what was left out and how to narrow your question, such as asking for one section, a shorter time period, a filter, or `response_format: concise`. The Lifesight product always shows the full result.
- **Rate limits apply** to each member in each workspace, and separately to sign-in. If you go over the limit, you'll get a 429 response and Claude will try again shortly. In normal use, you shouldn't notice this.
- **Session length:** your access token refreshes on its own while you use the connector. If you don't use it for a long time, the connection expires and you'll be asked to sign in again. Until then, it keeps your selected workspace and conversation threads.
- **Personal access tokens** expire, and you can revoke them from **Settings → MCP**.

You can see the current values for each of these in the console under **Settings → MCP**.

***

## Troubleshooting

### Most tools suddenly fail with a message about additional properties

If almost every tool returns an error like `data must NOT have additional properties`, your app is checking results against an old copy of our schema. It saved that copy when you first connected, and we've since added a new field.

**Fix:** remove the connector and add it again. Server updates don't fix a connection that's already open. Only reconnecting refreshes the saved schema and tool list.

<Callout icon="📌" theme="default">
  ### **Reconnect in every app you use.** Claude.ai, Claude Desktop and Claude Code each keep their own saved copy. Reconnecting in one app doesn't fix the others.
</Callout>

### A write is refused even though my admin gave me access

Your access is set when you sign in. If your admin gave you access after you connected, remove the connector and add it again. If it still fails, ask your admin to check that **Settings → MCP** shows write or decide access for that workspace. Access is set per workspace, not per account.

### "Workspace … is not one you hold"

Your workspaces are added when you connect. If you were added to this workspace later, remove the connector and add it again. If it still happens, ask your admin to make sure your membership is active and not still a pending invite.

### "MCP is switched off for this workspace by its admin"

An admin has turned off the connector for this workspace in **Settings → MCP**. Your other workspaces aren't affected. Use `switch_workspace` to move to a workspace where it's turned on.

### "… cannot be served right now: its MCP settings could not be read"

This is a different issue. We couldn't read the workspace's settings, so we pause access instead of guessing. This usually clears up quickly. Try again in a little while. Nobody needs to change anything.

### A result looks cut off

Large results are shortened to fit. Check the warnings, which tell you what was left out and how to narrow your question. Asking for one section, a shorter time period, or a single channel usually gets you the full result.

### Claude says it can't answer because there's no model

Most questions need a champion marketing mix model in your workspace. Without one, you can still ask about data health, experiments and saved plans. Promote a model in the product to unlock everything else.

### Sign-in opens but never finishes

Make sure your browser isn't blocking the pop-up, and that you're signing in to the Lifesight account that has the workspace you want. If your organization limits outside network access, allow `ask.lifesight.io`.

***

## Privacy and security

- **What Claude receives:** only the results of the tools it uses, from the workspace you've selected, and only within your permissions. Lifesight reads your workspace using your sign-in. Your marketing data warehouse is read by Lifesight using its own service credentials, limited to your workspace's dataset.
- **What Lifesight receives and stores:** the inputs to each tool request, including your question when you start an Ask Lifesight investigation, along with the results. These are saved in a thread linked to your account and workspace. Lifesight also keeps one audit record per request. It shows who made the request, which workspace, which assistant, which tool, a one-way digest of the inputs, the result and how long it took. The audit record doesn't include the inputs themselves.
- **What Lifesight does not receive:** the rest of your conversation with the assistant, your other files, or your other connected services.
- **How long data is kept:** threads and audit records are kept for two years.
- **Sign-in:** uses OAuth 2.1 with PKCE. No API key is created or stored. The assistant never sees your Lifesight password.
- **Revoking access:** disconnect in your assistant, or revoke access from **Settings → MCP** in the Lifesight console. An admin can also turn off the connector for a whole workspace from the same page.

You can find full details in the Lifesight privacy policy.

***

## FAQs

### Can Claude see data I can't see?

No. Every request is limited to the workspace you've selected, and your membership and permissions are checked before anything is read.

### Can Claude spend money or change my ad campaigns?

No. There's no tool that can transfer money, make a payment, or change spend on an ad platform. The most a change can do is propose a plan, which you then approve inside the Lifesight product.

### Where do the numbers come from?

Always from the Lifesight platform. Claude is not allowed to calculate business numbers. Every result includes a `provenance` block that shows where each number came from, along with its unit and currency. You can also ask Claude to run `check_figures` on any draft, and it will tell you which numbers are actually backed by the results in that conversation.

### Can I use it with more than one workspace?

Yes. Every workspace you belong to is included. Switch by just asking, or name a workspace for a single question.

### Can my whole team use it?

Yes. Each person connects with their own account and sees only what their permissions allow. Admins decide, for each workspace, whether the connector is on, which assistants can use it, and whether connections can make changes.

### Does it work in ChatGPT or other assistants?

It's a standard MCP server, so any app that supports streamable HTTP and OAuth can connect. Workspace admins choose which assistants are allowed for each workspace.

### What happens to a conversation thread?

It belongs to your account and workspace. It shows up in your Lifesight conversation list next to your product conversations, so you can go back and see what Claude asked and what came back.

***

**Still stuck?** Ask Claude to raise a ticket for you, for example "Raise a support ticket about this," and check its progress with `get_support_ticket_status`. You can also contact Lifesight support the usual way through the console.

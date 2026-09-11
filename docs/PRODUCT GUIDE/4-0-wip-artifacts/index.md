---
title: '[4.0][WIP] Artifacts'
excerpt: >-
  Turn any question into a live dashboard, report, deck or page built from your
  workspace data — or upload one you already have.
hidden: true
metadata:
  title: Create and Share Artifacts in Lifesight
  keywords:
    - Lifesight
    - Artifacts
    - Dashboards
    - Reports
---
An **artifact** is something you can hand to someone else: a live dashboard, a static page, a PDF report or a slide deck. Artifacts live under **Artifacts** in the left navigation.

There are two ways one gets there. You can **describe what you want** and let Lifesight build it from your live workspace data, or you can **upload a file you already have**. The first gives you something that refreshes itself; the second gives your existing reporting one address next to everything else.

![The Artifacts page — the composer, your recent artifacts, and the template library](https://files.readme.io/c608d1aae7a039e74b14420643aba24aad7395eafcc3be9c7030e4923e0f5762-artifacts-landing.png)

<Callout icon="📘" theme="info">
  You do not build a generated artifact by dragging widgets onto a blank grid. You describe it in plain English, Lifesight runs the analysis on your live workspace, and the canvas is assembled from the result. **Every number on it comes from your data.**
</Callout>

***

## The four output formats

| Format | What it is | Best for |
| ---------------- | ---------------------------------------------------------------------- | --------------------------------------------- |
| **Live page** | A dashboard bound to live data — regenerate it to pull the latest numbers | Standing dashboards, monitoring, pacing trackers |
| **Static page** | A page rendered once and frozen | Snapshots, recaps, post-mortems |
| **PDF** | A paginated document | Reports, memos, one-pagers, briefs |
| **Presentation** | A stack of 16:9 slides | QBRs, board reviews, leadership decks |

<Callout icon="📘" theme="info">
  You do not pick the format — your words do. Say **deck**, **slides**, **presentation** or **QBR** and you get a presentation. **Report**, **PDF**, **memo** or **one-pager** gives you a PDF. **Snapshot**, **summary** or **recap** gives a static page. Anything else — and anything mentioning **live**, **dashboard**, **real-time** or **tracker** — gives a live page.

  If you get the wrong shape, say the format word explicitly and generate again.
</Callout>

***

## Four ways to create an artifact

| Route | Use it when |
| ------------------------- | --------------------------------------------------- |
| **From the composer** | You know what you want to build |
| **From a template** | You want a proven layout to start from |
| **From an answer in Ask** | You already asked the question and like the answer |
| **By uploading a file** | The thing already exists outside Lifesight |

### From the composer

1. Go to **Artifacts**.
2. In the box under **What will you create today?**, describe the artifact — for example `Create a live CMO dashboard with revenue, ROAS and channel mix`.
3. Press **Enter**.
4. The editor opens and building begins. Cards land on the canvas as they are computed.

The chips under the composer are starter prompts. Click one to drop it into the box, then edit before sending.

<Callout icon="👍" theme="okay">
  Be specific about the metrics and the cut. "Revenue and ROAS by channel for the last 90 days, plus a weekly trend" produces a far better first draft than "a performance dashboard". You can always refine it afterwards in the chat.
</Callout>

Sometimes one detail cannot be guessed — a date range, a market, which KPI you mean. The canvas then asks for it. Nothing is built from the question itself: answer in the panel on the right, and the artifact is generated from your answer.

### From a template

Templates are ready-made layouts, one per output format.

| Template | Format | What is on it |
| ------------------------------- | ------------ | ------------------------------------------------------------------- |
| **CMO Dashboard** | Live page | Revenue, blended ROAS, spend and conversion KPIs; revenue and ROAS by channel |
| **Pacing Recommendations** | Static page | This week's pacing read, spend and CPA KPIs, daily spend trend |
| **QBR Deck** | Presentation | Title slide, quarterly revenue, revenue by channel, spend mix, scorecard |
| **Ad Channel Performance Report** | PDF | Narrative summary, spend and blended CPA, ROAS by channel, detail table |

Scroll to **Templates** on the Artifacts page, or click **See all** for the full library, where you can search and filter by **Executive**, **Performance** or **Analytics**. Click **Use template** and the editor opens on it immediately.

### From an answer in Ask

This is the fastest route, because the analysis already exists.

1. Ask a question anywhere — the Cockpit, the docked **Ask** panel, or the fullscreen Ask view.
2. Under the answer, click **Add to artifact**.
3. Choose **New artifact**, or pick an existing one to add to.
4. Add any extra direction — this is where you say "a board-ready deck" or "focus on Q4 efficiency".
5. Click **Create artifact**.

The editor opens with the Ask panel already carrying the conversation that produced the answer, so you can keep refining without re-explaining anything.

<Callout icon="📘" theme="info">
  You can also just ask for it. Typing "create a report of this conversation" or "turn this into a deck" inside Ask builds the artifact from everything discussed so far.
</Callout>

### By uploading a file

Bring in an HTML page, a PDF or a PowerPoint deck you already have.

1. On the Artifacts page, click **Upload**.
2. Choose your file — drag it onto the dialog, or click to browse.
3. Give it a name. The filename is filled in for you with the extension removed.
4. Click **Add to repository**.

![The upload dialog, with a file picked and its name ready to edit](https://files.readme.io/b5563134cbd0324b39c792f80514347328e94d816cbfc1ab04b5742029cb8c41-artifacts-upload-dialog-only.png)

| Format | Extensions | What happens when someone opens it |
| ------------------- | ---------------- | ---------------------------------------------------------- |
| **HTML page** | `.html`, `.htm` | Renders in the page |
| **PDF document** | `.pdf` | Renders in the page |
| **PowerPoint deck** | `.pptx` | Offered as a download — browsers cannot show a deck inline |

Files can be up to **25 MB**.

<Callout icon="📘" theme="info">
  An uploaded artifact is **presentation-only**. There is no canvas and no chat editing, it is stored exactly as it arrived, and it downloads as the file that went in. Renaming it never touches the file. Uploaded HTML runs in a sandbox and cannot read your Lifesight session.
</Callout>

***

## The artifact editor

Generated artifacts open in the editor: the canvas on the left, the **Ask** panel on the right.

### Toolbar

| Control | What it does |
| -------------- | ----------------------------------------------------------------------------- |
| **Name** | Click the title to rename. **Enter** saves, **Esc** cancels. |
| **Regenerate** | Re-runs the analysis and brings in the latest numbers |
| **Share** | Copy a private link, or create, copy and revoke a public read-only link |
| **Export** | Download as HTML, PDF or PPTX |
| **Pin** | Pin the artifact to the left sidebar |
| **Save** | Save it into your artifacts. Reads **Saved** once it is up to date. |

The line next to **Regenerate** tells you the state of the data — when it was last refreshed, and whether the last run replaced the layout or only swapped the numbers.

### Editing with the chat

Two different things happen depending on what you say:

* **Ask for a change** and the canvas updates itself — `Add a ROAS by channel breakdown`, `Focus on the top 5 channels only`.
* **Ask a question** and it is answered in the chat, leaving the canvas alone.

When an answer contains data worth keeping, click **Add this answer to the canvas** underneath it.

### Arranging the canvas

Live and static pages sit on a 12-column grid you can rearrange. Your arrangement is respected everywhere the artifact is seen — shared links and exports included — and widgets you have positioned yourself survive the next regeneration.

| Action | How |
| --------------------- | ------------------------------------------- |
| Move a widget | Drag it by its move handle |
| Resize a widget | Drag the right, bottom or bottom-right handle |
| Move with the keyboard | Select it, then **← ↑ → ↓** |
| Resize with the keyboard | Select it, then **Shift + ← ↑ → ↓** |
| Remove a widget | Click its **×**, or select it and press **Delete** |

<Callout icon="📘" theme="info">
  PDFs and decks are laid out by their format — a document page and a slide stack — so there is no free grid to drag within. Drag and resize are desktop-only; below tablet width the canvas stacks into a single column.
</Callout>

***

## Saving and drafts

**Every generated artifact starts as a draft.** It is not in your artifacts list until you click **Save**. Unsaved drafts are found under the **Drafts** tab, which is the only place they appear. Uploads are not drafts — they are saved the moment they arrive.

***

## Sharing

Open the **Share** menu on any artifact:

| Option | Who can open it |
| --------------------------- | --------------------------------------------------- |
| **Copy private link** | Only people who can sign in to your workspace |
| **Create / Copy public link** | Anyone with the link — read-only, no sign-in needed |
| **Revoke public link** | Stops the public link resolving, immediately |

<Callout icon="🚧" theme="warn">
  **Where artifacts live today.** In this release the artifact repository is stored in the browser it was created in. A share link therefore only resolves in that browser, and artifacts do not yet follow you between devices.

  Export or download when you need to send something that has to open anywhere.
</Callout>

***

## Exporting and downloading

A **generated** artifact can be exported in any of three formats, whatever its own format is:

| Export | What you get |
| ------ | -------------------------------------------------------- |
| **HTML** | A self-contained page — charts embedded, opens anywhere |
| **PDF** | The canvas as a paginated document |
| **PPTX** | One slide per chart, with native PowerPoint charts |

An **uploaded** artifact has **Download** instead. It converts to nothing else: what was uploaded is what comes back, under its original filename.

![An uploaded HTML page, rendered read-only with Share, Download and Pin](https://files.readme.io/decf94d4b33462260b8a526a779be9b398cbad7ee610edcdc8b089e99ed899c0-artifacts-uploaded-view.png)

***

## Managing your artifacts

The Artifacts page shows your most recent artifacts. Click **See all** for the full list.

![The full list — generated and uploaded artifacts side by side](https://files.readme.io/cec43ac000501e96b9f548806744ad8934001aff18500d4d074bc05d6657de89-artifacts-list.png)

In the list you can:

* **Search** by name, or by the prompt that created the artifact.
* Switch between **All**, **Yours**, **Drafts** and **Shared with you**.
* **Pin** or **Unpin** from the **⋯** menu on any card.
* **Delete** from the same menu.

Cards show a preview, the format, and — for uploads — an **Uploaded** badge.

***

## What to ask for

| You want | Ask for |
| -------------------------- | -------------------------------------------------------------------------------- |
| A standing executive view | `A live CMO dashboard with revenue, ROAS, spend mix and channel trend for the last 90 days` |
| A weekly readout | `A static summary of last week's performance by channel with the biggest movers called out` |
| Something to present | `A QBR deck covering quarterly revenue, channel mix and what changed vs last quarter` |
| A document for the inbox | `A PDF report on paid channel efficiency over the last 30 days, with recommendations` |
| To watch budget | `A live tracker of budget pacing against plan by channel` |

***

## Troubleshooting

<Callout icon="📘" theme="info">
  **The canvas is empty.** If building finished and nothing landed, ask for the content directly in the panel — for example "add revenue, ROAS and spend KPIs, then a revenue trend by channel".
</Callout>

<Callout icon="📘" theme="info">
  **Regenerate rebuilt my layout instead of just updating the numbers.** That happens when the new analysis no longer matches the charts on the canvas. The alternative would be leaving charts showing numbers that are no longer theirs. Re-apply your arrangement and it will be respected on subsequent runs.
</Callout>

<Callout icon="📘" theme="info">
  **My artifact is not in the list.** It is probably still a draft. Open the **Drafts** tab, open it, and click **Save**.
</Callout>

<Callout icon="📘" theme="info">
  **My upload was rejected.** Only `.html`, `.htm`, `.pdf` and `.pptx` are accepted, under 25 MB and not empty. Re-save older Office formats, or export to PDF.
</Callout>

<Callout icon="🚧" theme="warn">
  **The uploaded file is no longer stored in this browser.** The artifact's record outlived the file behind it — usually because browser storage was cleared, or the artifact was created in a different browser. Upload the file again.
</Callout>

---
title: '[4.0][WIP] Artifacts (Manual Upload)'
excerpt: >-
  Bring an HTML page, PDF or PowerPoint deck into Lifesight, and share it from
  the same place as everything else your team works from.
hidden: true
metadata:
  title: Upload and Share Artifacts in Lifesight
  keywords:
    - Lifesight
    - Artifacts
    - Upload
    - Share
---
An **artifact** is something you can hand to someone else: a dashboard, a report, a deck, a page. Artifacts live under **Artifacts** in the left navigation.

Most reporting lives in the tool that made it. A quarterly deck sits in someone's Drive, last month's PDF is in an inbox, and the dashboard is a link that only half the team has. Artifacts gives them one address, next to the data they were built from.

In this release you bring artifacts in by **uploading a file you already have**. You keep making them wherever you make them today — the upload puts them somewhere your team can find them.

![Your artifacts — everything uploaded to the workspace, with the Upload button in the header](https://files.readme.io/68020558eea779d32aeaf85bb42d3138e514bb42dc6ddc5f0d998699983d6bea-artifacts-list-uploads-only.png)

***

## What you can upload

| Format | Extensions | What happens when someone opens it |
| ---------------------- | ----------------- | ----------------------------------------------- |
| **HTML page** | `.html`, `.htm` | Renders in the page |
| **PDF document** | `.pdf` | Renders in the page |
| **PowerPoint deck** | `.pptx` | Offered as a download — browsers cannot show a deck inline |

Files can be up to **25 MB**.

<Callout icon="📘" theme="info">
  An uploaded artifact is **presentation-only**. It is stored exactly as it arrived and handed back exactly as it arrived: no editing, no charts to rearrange, and no conversion between formats. A PDF that goes in is the PDF that comes out.
</Callout>

***

## Uploading a file

1. Go to **Artifacts** in the left navigation.
2. Click **Upload** at the top right of the page.
3. Choose your file — drag it onto the dialog, or click to browse.
4. Give it a name. The filename is filled in for you with the extension removed, and you can change it to whatever your team will search for.
5. Click **Add to repository**.

![The upload dialog, with a file picked and its name ready to edit](https://files.readme.io/b5563134cbd0324b39c792f80514347328e94d816cbfc1ab04b5742029cb8c41-artifacts-upload-dialog-only.png)

The artifact opens as soon as it is saved. It also appears in your artifacts list straight away — uploads are not drafts, so there is nothing further to save.

<Callout icon="👍" theme="okay">
  Name it for the reader, not the file. `Q3 Board Review — EMEA` is easier for a colleague to find than `qbr_v4_final_FINAL.pptx`. Renaming never touches the file: it still downloads under its original filename.
</Callout>

***

## Viewing an uploaded artifact

Open an artifact from the list and you get the file itself, with a small toolbar above it.

![An uploaded HTML page, rendered in the workspace with its toolbar above it](https://files.readme.io/decf94d4b33462260b8a526a779be9b398cbad7ee610edcdc8b089e99ed899c0-artifacts-uploaded-view.png)

| Control | What it does |
| ----------------------- | ------------------------------------------------------------------------ |
| **Name** | Click the title to rename it. **Enter** saves, **Esc** cancels. |
| **Manually uploaded** | A badge marking this as an upload rather than something built in Lifesight |
| **Share** | Copy a private link, or create, copy and revoke a public read-only link |
| **Download** | Hand back the original file, under its original name |
| **Pin** | Pin it to the left sidebar for one-click access |

Under the toolbar you will see the format, the file size and the original filename, so it is obvious what you are looking at and what will download.

<Callout icon="📘" theme="info">
  Uploaded HTML runs in a sandbox. Scripts inside the page cannot read your Lifesight session or reach anything else in the app. This is why an uploaded page that expects to talk to its original host may render without its data.
</Callout>

***

## Sharing

Open the **Share** menu on any artifact:

| Option | Who can open it |
| --------------------------- | -------------------------------------------------- |
| **Copy private link** | Only people who can sign in to your workspace |
| **Create / Copy public link** | Anyone with the link — read-only, no sign-in needed |
| **Revoke public link** | Stops the public link resolving, immediately |

A public link opens a clean read-only view with the artifact name and a **Shared · read-only** badge. There is no editing and no app navigation around it.

<Callout icon="🚧" theme="warn">
  **Where artifacts live today.** In this release the artifact repository is stored in the browser it was created in. A share link therefore only resolves in that browser, and artifacts do not yet follow you between devices or teammates.

  When you need something that has to open anywhere, use **Download** and send the file.
</Callout>

***

## Managing your artifacts

The Artifacts page shows your most recent artifacts. Click **See all** for the full list. In the list you can:

* **Search** by name.
* Switch between **All**, **Yours** and **Shared with you**.
* **Pin** or **Unpin** from the **⋯** menu on any card. Pinned artifacts appear under **Pinned** in the left sidebar.
* **Delete** from the same menu.

Every card shows the format, an **Uploaded** badge, and when it was last updated.

***

## Troubleshooting

<Callout icon="📘" theme="info">
  **My file was rejected.** Only `.html`, `.htm`, `.pdf` and `.pptx` are accepted, and the file must be under 25 MB and not empty. If you have a `.ppt` or `.doc`, re-save it in the modern format, or export it to PDF.
</Callout>

<Callout icon="📘" theme="info">
  **My deck will not display.** That is expected. No browser renders a PowerPoint file inline, so a `.pptx` artifact shows a download card instead. Export it to PDF before uploading if you need it to display in the page.
</Callout>

<Callout icon="🚧" theme="warn">
  **The file is no longer stored in this browser.** The artifact's record outlived the file behind it — usually because browser storage was cleared, or because the artifact was created in a different browser or on a different device. Upload the file again.
</Callout>

<Callout icon="📘" theme="info">
  **My uploaded page looks broken.** An HTML file that pulls its charts, fonts or data from the server it used to live on will not find them here. Export a self-contained version — one with everything embedded — and upload that.
</Callout>

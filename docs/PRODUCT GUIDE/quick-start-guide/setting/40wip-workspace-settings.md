---
title: '[4.0][WIP] Workspace Settings'
excerpt: >-
  Settings > Workspace carries the workspace reporting defaults and the one-time
  week start lock.
deprecated: false
hidden: true
metadata:
  robots: index
---
**Settings > Workspace** holds the reporting defaults, the day each reporting and week begins.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Everyone can open the tab and read every row. **Set & lock** needs Workspace Admin; denied, it shows `Your role (<Role>) cannot update workspace settings.`<br />**Where:** Sidebar user menu > **Settings** > **Workspace**
  **Time:** About 2 minutes.
</Callout>

## Before you start

- You are signed in to the workspace.
- **Settings** is open on the **Workspace** tab.
- For the lock, the **Week start day** row still shows a select and **Set & lock**.

## See your reporting defaults

<Callout icon="📘" theme="info">
  ### **Role:** Everyone
</Callout>

1. In the sidebar, open the user menu and select **Settings**.
2. Select the **Workspace** tab.
3. Read the **Timezone** and **Default Currency** rows on the **Workspace** card.

Both rows are greyed out, with a `View only` tooltip on the information icon, and neither opens for any role.

## Lock the week start day

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin for **Set & lock**
</Callout>

The **Week start day** row says `This can be set only once. After that, contactthe Lifesight team to change it.` [Models](doc:glossary) and the weekly data quality checks use this day.

1. On **Settings > Workspace**, find the **Week start day** row.
2. Select a day. The list offers **Monday**, **Tuesday**, **Wednesday**, **Thursday**, **Friday**, **Saturday** and **Sunday**, and starts on **Monday**. The selection is not stored until you lock it; leave the page without **Set & lock** and the row returns to **Monday**.
3. Select **Set & lock**.
4. In **Lock reporting week start?**, enter the day name exactly as the list writes it.
5. Select **Lock**.

**Cancel** closes the dialog and changes nothing.

You're done when:

- The toast `Reporting week start locked to <Day>` has appeared.
- The **Week start day** row shows a lock pill carrying the day you chose.
- The line `Locked on DD Mon YYYY. Contact Lifesight to change.` sits under the row description, for example `Locked on 12 Sep 2026.`

<Callout icon="❗️" theme="error">
  ### This is a one time action

  **Set & lock** records the day this browser shows as the reporting week start, and the tab has no unlock control afterwards. That is why the dialog makes you type the day name first. To move a locked week start, Edit the brand kit
</Callout>

## Reference

| Row                  | Value shown                                           | Helper text on the row                                                                  | Who can change it                        |
| -------------------- | ----------------------------------------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------- |
| **Timezone**         | `Asia/Kolkata`                                        | `Used for reporting and scheduled tasks.`                                               | Contact Lifesight                        |
| **Default Currency** | `USD`                                                 | `Currency shown in metrics and exports.`                                                | Contact Lifesight                        |
| **Week start day**   | **Monday**, until a Workspace Admin locks another day | `The day each reporting week begins on. Used by Models and weekly data quality checks.` | Only a Workspace Admin can lock it, once |

## FAQ

### Why can't I change the timezone or the currency?

**Timezone** and **Default Currency** are view-only for every role, Workspace Admin included. Contact Lifesight to change them.

### Should I lock the week start day now, or wait?

Lock it once your reporting calendar is agreed. Waiting costs nothing — the day stays **Monday** and nothing on the tab nags you. Locking early costs a call to Lifesight.

### I locked the wrong day. How do I unlock it?

You will have to contact Lifesight, to change.

## Related

<Cards columns="2">
  <Card title="Your profile and preferences" href="doc:your-profile-and-preferences" icon="fa-user-gear">
    The settings that belong to you, not the workspace.
  </Card>

  <Card title="Notifications" href="doc:notifications" icon="fa-bell">
    The bell, the log, and the Slack dialog on this tab.
  </Card>

  <Card title="Switch and create workspaces" href="doc:switch-and-create-workspaces" icon="fa-layer-group">
    Which workspace these settings sit beside.
  </Card>

  <Card title="What's live in this build" href="doc:whats-live-in-this-build" icon="fa-circle-half-stroke">
    What saves, what stays in this browser, what only previews.
  </Card>
</Cards>

## Agent card

```yaml agent
task: settings-workspace
title: Workspace settings and brand kit
type: howto
surface: Settings
page: https://docs.lifesight.io/docs/workspace-settings
last_verified: 2026-09-13
app_build: "ls4x@feature/LS4X-155"

state: browser
persistence: browser_local
state_note: >
  The week start lock and the brand kit are written to this browser's local
  storage and are never sent to a server. They do not follow the user to another
  browser, another device or a colleague, and they are not scoped to the active
  workspace. Nothing else in the product reads either one: no export, report,
  chart or artifact uses the brand kit, despite the row descriptions naming
  exports and artifacts. Timezone and Default Currency are fixed display values
  that no role can edit.

requires_role: [Workspace Admin]
requires_rights: [settings.update_workspace_settings, settings.configure_brand_kit]
denied_ux: >
  Every role can open the tab and read every row, and every role can change the
  day in the "Week start day" select. "Set & lock" stays visible at 50% opacity
  with the tooltip "Your role (<Role>) cannot update workspace settings. Ask a
  workspace admin for access."; "Upload" and "Remove" do the same with
  "Your role (<Role>) cannot configure brand kit. Ask a workspace admin for
  access." Both print the internal role value such as "DataPractitioner".
  "Company name", the colour swatches, "Heading font" and "Body font" are greyed
  out with no tooltip. Without the right, the lock dialog cannot open at all.

entry_point: "Sidebar user menu > Settings > Workspace"
url: "/settings?tab=workspace"
preconditions:
  - Signed in to the workspace.
  - The Settings page is open on the Workspace tab.
  - For the lock, the Week start day row still shows a select and "Set & lock".

ui_strings:
  tab: "Workspace"
  workspace_rows: ["Timezone", "Default Currency", "Week start day"]
  week_start_options: ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
  lock_action: "Set & lock"
  dialog_title: "Lock reporting week start?"
  dialog_confirm: "Lock"
  dialog_cancel: "Cancel"
  brand_kit_section: "Brand kit"
  brand_kit_rows: ["Company name", "Logo", "Color palette", "Heading font", "Body font"]
  logo_actions: ["Upload", "Remove"]
  font_options: ["Sans-serif", "Serif", "Monospace"]
  footer_actions: ["Discard changes", "Save changes"]
  slack_section: "Slack Integration"
  slack_row: "Configure notifications on slack"

confirm_phrase: 'The day label exactly as the select writes it, for example "Monday". Case-sensitive; "Lock" stays disabled until it matches.'

procedures:
  - id: see-your-reporting-defaults
    goal: Read the workspace reporting defaults.
    steps:
      - 'In the sidebar, open the user menu and select "Settings".'
      - 'Select the "Workspace" tab.'
      - 'Read the "Timezone" and "Default Currency" rows on the Workspace card.'
    expect: 'Timezone shows "Asia/Kolkata" and Default Currency shows "USD". Both selects are greyed out, and the information icon beside each one shows the tooltip "View only".'
    verify: 'Neither select opens on click, for any role.'
    on_fail: 'None. There is nothing to change here; tell the user to contact Lifesight.'
    reversible: true
    undo: 'Not applicable — nothing is written.'
  - id: lock-the-week-start-day
    goal: Record the day this browser shows as the start of the reporting week, once and for all.
    steps:
      - 'On "Settings > Workspace", find the "Week start day" row.'
      - 'Select a day. The list offers "Monday" through "Sunday" and starts on "Monday". The selection is not stored until it is locked; leaving the page without "Set & lock" returns the row to "Monday".'
      - 'Select "Set & lock".'
      - 'In "Lock reporting week start?", enter the day name exactly as the list writes it.'
      - 'Select "Lock".'
    expect: 'Toast "Reporting week start locked to <Day>".'
    verify: 'The Week start day row shows a lock pill with the day, and the line "Locked on DD Mon YYYY. Contact Lifesight to change." for example "Locked on 12 Sep 2026."'
    on_fail: '"Lock" stays disabled while the typed text does not match the day label exactly. The match is case-sensitive. Return to step 4, or select "Cancel" to leave everything as it was.'
    reversible: false
    undo: 'None in-product. The tab has no unlock control; the user must contact Lifesight.'
  - id: edit-the-brand-kit
    goal: Set the company name, logo, colours and fonts held in this browser.
    steps:
      - 'On "Settings > Workspace", go to the "Brand kit" card.'
      - 'In "Company name", enter the name you want.'
      - 'Optional: on the "Logo" row, select "Upload" and choose a PNG, JPEG or SVG file.'
      - 'On the "Color palette" row, select a swatch and pick a colour.'
      - 'In "Heading font", select "Sans-serif", "Serif" or "Monospace".'
      - 'In "Body font", select "Sans-serif", "Serif" or "Monospace".'
    expect: 'Each row shows the new value immediately, and the footer "You have unsaved changes" appears at the bottom of the page.'
    verify: 'The Brand kit rows carry the values entered after switching tabs and returning.'
    on_fail: 'No validation exists. An empty company name is accepted, and a logo large enough to exceed the browser storage quota fails without a message.'
    reversible: true
    undo: 'Re-enter the previous values by hand. "Discard changes" resets to factory defaults, not to the previous values.'
  - id: save-or-discard-changes
    goal: Clear the unsaved-changes footer.
    steps:
      - 'Edit any "Brand kit" row.'
      - 'Read the footer at the bottom of the page: "You have unsaved changes".'
      - 'Select "Save changes".'
    expect: 'Toast "Capabilities saved". The footer disappears.'
    verify: 'The footer does not return until a Brand kit row, or the Customize Menu selection on the Preferences tab, changes again.'
    on_fail: 'None. The save cannot fail; it writes nothing to a server.'
    reversible: true
    undo: 'Not applicable. The edits were already stored as they were made.'

limits:
  - Timezone and Default Currency are fixed at "Asia/Kolkata" and "USD" and are view-only for every role.
  - The week start lock is stored per browser, not per workspace, and no other screen reads it.
  - The brand kit logo is held in this browser as a data URL. Nothing checks its size before storing it, and a file over roughly 3 MB can exceed the browser's storage quota and fail without a message.
  - '"Discard changes" resets the brand kit to factory defaults: "NovaBrand", colours #3b82f6, #10b981, #f59e0b, #ffffff and #1a1a1a, and no logo. It also returns the Customize Menu selection on the Preferences tab to the last saved set.'
  - The Color palette row has exactly five swatches, labelled P, S, A, B and T.

agent_rules:
  - Do not tell the user the brand kit is used in exports, reports, charts or artifacts. Nothing reads it.
  - Do not tell the user the week start lock or the brand kit is saved for the workspace. Both live in that one browser.
  - Treat the week start lock as irreversible. Show the confirm phrase and the consequence, and ask the user before advising it.
  - Do not offer a way to change Timezone or Default Currency. No role can; tell the user to contact Lifesight.
  - Do not advise "Discard changes" as an undo. It restores the brand kit's factory defaults, not the user's last saved values, and also reverts the Customize Menu selection on the Preferences tab.

related: [your-profile-and-preferences, notifications, switch-and-create-workspaces, whats-live-in-this-build, glossary]
```

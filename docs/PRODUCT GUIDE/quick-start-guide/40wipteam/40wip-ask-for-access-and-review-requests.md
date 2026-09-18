---
title: '[4.0][ReadyForQA] Ask for access, and review requests'
excerpt: >-
  Ask for Read or Manage access from the Access Restricted page, then approve or
  reject the request on Team > Access Requests.
deprecated: false
hidden: true
metadata:
  robots: index
---
An access request asks for one module your role does not open; a Workspace Admin answers it. It starts on **Access Restricted** and lands on **Team > Access Requests**. This page covers both halves, plus the three unrelated controls also labeled **Request Access**.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Everyone can raise a request.
  **Approve or reject:** Workspace Admin only (`team.edit_permissions`). Every other role sees the full list with **Approve** and **Reject** dimmed and the tooltip `Your role (<Role>) cannot edit permissions. Ask a workspace admin for access.`<br />**Time:** About a minute on each side.
</Callout>

## How a request travels

A denied module opens **Access Restricted**, where **Request Access** creates a pending request that a Workspace Admin approves or rejects.

<Tabs>
  <Tab title="If you hit Access Restricted">
    A module your role cannot open stays visible at 50% opacity — **Data**, **Profiles**, **Segments** and **Config** in the **Hub** dropdown at the bottom of the sidebar, the rest in the sidebar itself — and opens the **Access Restricted** page instead.
  </Tab>

  <Tab title="If you're a Workspace Admin">
    Requests land on **Team > Access Requests**, whose tab label carries an amber badge.
  </Tab>
</Tabs>

## Request access to a module

<Callout icon="📘" theme="info">
  ### **Role:** Everyone. Nothing in this dialog is gated.
</Callout>

1. In the sidebar or **Hub** dropdown, select the dimmed module.
2. On **Access Restricted**, select **Request Access**.
3. Select **Read access** or **Manage access**.
4. Optional: add a reason in **Why do you need this access? (optional)**.
5. Select **Send request**.

**Send request** stays disabled until you select a card and reads **Sending…** while it works. On success the toast `Access request sent to your admin` appears, the dialog closes, and your name shows under **PENDING** on **Team > Access Requests**. If it reads `Failed to send request. Please try again.`, return to step 5.

Sending also raises the notification `Access request from <Name>` in the Notification pannel under the **Access** category, linking to **Team > Access Requests**.

## Review a request

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin&#x20;
</Callout>

1. In the sidebar, open the user menu and select **Team**.
2. Select the **Access Requests** tab.
3. Under **PENDING**, find the request by the person's name and the line `<Permission> · <Module>`.
4. Select **Approve**.
5. In `Approve access request?`, read which role the person moves onto. If it names no role, the requester has no matching **Manage Team** record and approving changes no role.
6. Select **Approve**.

To decline instead, select **Reject** at step 4 — no confirmation dialog; the card
moves to **REVIEWED** at once.

An approval shows the toast `Access granted to <Name>` — with the description `Created role “<Role>”.` or `Assigned existing role “<Role>”.` when a **Manage Team** record matched — and the card moves to **REVIEWED&#x20;**&#x72;eading `Approved by WorkspaceAdmin`. A rejection shows `Request rejected` and thecard reads `Rejected by WorkspaceAdmin`. Every review is recorded as
`WorkspaceAdmin`, whoever performed it.

Approving needs building a custom role named `{Base role} + {Module}` — Executive plus Data becomes `Executive + Data` — that keeps everything the current role allows and adds the module; the member record on **Manage Team** moves onto it. A second approval extends the name, as in `Executive + Data + Config`. When the requester matches no **Manage Team** record, no role is generated, no member record changes, and the toast carries no description. The role lives in the browser tab you approved from.

Approving also records a permission grant on the server, readable by any admin under **Team > Manage Team > Edit Permissions** from any browser.

If the toast reads `Failed to approve request`, the approval did not go through — usually the request was already reviewed elsewhere, but also if the server is unreachable. Return to step 2 and re-read the list. `Failed to reject request` works the same way.

## Reference

| Stage                       | Where it shows                                            | What it means                                                      | Who acts next                                     |
| --------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------- |
| Access Restricted           | The module page                                           | Your role has no readable part of this module                      | You, with **Request Access**                      |
| Request Access              | The dialog `Request access to {Module}`                   | The right and reason are not sent yet                              | You, with **Send request**                        |
| Pending                     | **Team > Access Requests > PENDING**                      | On the server, counted in the amber tab badge                      | A Workspace Admin, with **Approve** or **Reject** |
| Approve                     | The dialog `Approve access request?`                      | The grant is confirmed, not yet applied                            | A Workspace Admin, with **Approve**               |
| Reject                      | The **REVIEWED** card                                     | Declined. No permission changed                                    | Nobody                                            |
| Generated role              | **Manage Team**, and **Manage Roles** in that browser tab | The requester's member record now sits on `{Base role} + {Module}` | Nobody                                            |
| Requester session unchanged | The requester's **Access Restricted** page                | An approval does not alter a signed-in session                     | Nobody                                            |

| Option        | Tag      | What it asks for                                       |
| ------------- | -------- | ------------------------------------------------------ |
| Read access   | `READ`   | `View {Module} — browse data, dashboards, and reports` |
| Manage access | `MANAGE` | `Edit and configure {Module} — includes read access`   |

A third tag, `ACTION`, exists on request cards for individual buttons, but the dialog never offers one — only these two are requestable.

Which modules send you to **Access Restricted**, by role:

| Role                | Modules that show Access Restricted |
| ------------------- | ----------------------------------- |
| Workspace Admin     | None                                |
| Data Practitioner   | Config                              |
| Marketing Scientist | Config                              |
| Strategic Planner   | Profiles, Data, Config              |
| Executive           | Profiles, Segments, Data, Config    |
| Viewer              | None                                |

**Settings**, **Team** and **Support** (`/help-center`) are open to every role, so they never show this page. A few surfaces outside the module list — **Generate Report** in the command palette, for example — also show **Access Restricted**, but their **Request Access** dialog offers no options, so no request can be sent. The full grid of role by module by right is on [Permissions matrix](doc:permissions-matrix-reference).

## FAQ

### My request was approved — why do I still see Access Restricted?

An approval moves your member record onto a new role and records a permission grant, but a signed-in session keeps the role it was given at sign-in. Nothing re-reads either when you open a module, so it stays closed. See [What's live in this build](doc:whats-live-in-this-build).

### Should I request access or ask for a different role?

Request access when your role fits your job and you need one extra module. Ask for a role change when the job changed and several modules are wrong. An approval adds one module to what you have; a role change replaces the whole set.

### Why does every reviewed request say WorkspaceAdmin?

Every review is recorded as `WorkspaceAdmin`, whoever pressed the button, so **REVIEWED** cards read `Approved by WorkspaceAdmin` or `Rejected by WorkspaceAdmin`. The actual admin's name is not stored anywhere you can read.

### Does the requester hear about my decision?

No message reaches the requester. The bell notification fires when a request is raised, not when it is reviewed, so tell the person yourself — especially after a rejection, since their **Access Restricted** page looks identical either way. The seeded `Access request approved` notification everyone sees is a demo, not a reply to anything you sent.

### Can I withdraw a request I sent?

A request cannot be withdrawn, edited or cancelled from your side, and it does not expire. A second request for the same module creates a second card, not a replacement. Ask a Workspace Admin to reject any you no longer need.

### The Access Requests tab is empty — where did the requests go?

Requests are held on the server in memory, so a server restart empties the list, reviewed cards included. With no seeded requests, a fresh environment shows `No pending requests` and `No reviewed requests yet` until someone raises one.

## Related

<Cards columns="2">
  <Card title="Roles and permissions" href="doc:roles-and-permissions" icon="fa-user-shield">
    Why a module is closed to you in the first place.
  </Card>

  <Card title="Invite, change, and deactivate teammates" href="doc:manage-your-team" icon="fa-user-plus">
    The other way to change what someone holds.
  </Card>

  <Card title="Create a custom role" href="doc:custom-roles" icon="fa-sliders">
    Where a generated role shows up afterwards.
  </Card>

  <Card title="What's live in this build" href="doc:whats-live-in-this-build" icon="fa-circle-half-stroke">
    What saves, what stays in this browser, what only previews.
  </Card>
</Cards>

## Agent card

```yaml agent
task: team-access-requests
title: Ask for access, and review requests
type: howto
surface: Team
page: https://docs.lifesight.io/docs/access-requests
last_verified: 2026-09-13
app_build: "ls4x@feature/LS4X-155"

state: preview
persistence: backend
state_note: >
  The request record, its status, the reviewer name and the timestamps are stored
  on the server in memory: they survive a page reload and are lost on a server
  restart. An approval also records a permission grant for the requester on the
  server, readable by any admin from any browser under Team > Manage Team > Edit
  Permissions; no module gate reads it, so the module still does not open. The
  member's new role on Manage Team is held in page memory and is gone on reload.
  The generated custom role is written to the approving browser tab's
  sessionStorage, so it survives a reload, disappears when the tab is closed, and
  is invisible to other admins. The requester's own session access never changes,
  because a signed-in session carries the role it was given at sign-in. The
  requester is never notified of the decision.

requires_role: []
requires_rights: [team.edit_permissions]
denied_ux: >
  Raising a request is open to every signed-in user. Reviewing is not: for any
  role other than Workspace Admin, "Approve" and "Reject" stay visible at 50%
  opacity with the tooltip "Your role (<Role>) cannot edit permissions. Ask a
  workspace admin for access.", where <Role> is the internal value without
  spaces, e.g. "DataPractitioner" — unlike denied_body's <Role spaced>, which is
  the same role with spaces, e.g. "Data Practitioner". The confirmation dialog
  refuses to open. The Access Requests tab itself, and every request on it, stays
  readable for all roles.

entry_point: "Access Restricted > Request Access; sidebar user menu > Team > Access Requests"
url: "/team?tab=requests"
preconditions:
  - Signed in to the workspace.
  - To request - a module the current role cannot open is on screen, showing Access Restricted.
  - To review - signed in as a Workspace Admin with the Team page open on the Access Requests tab.

ui_strings:
  denied_page: "Access Restricted"
  denied_body: "You don't have permission to view the <segment> module based on your current role (<Role spaced>)."
  request_button: "Request Access"
  request_dialog_title: "Request access to <Module>"
  request_dialog_description: "Your admin will be notified and can approve or reject your request."
  request_options: ["Read access", "Manage access"]
  request_reason: "Why do you need this access? (optional)"
  request_reason_placeholder: "Briefly describe your use case…"
  request_cancel: "Cancel"
  request_submit: "Send request"
  request_busy: "Sending…"
  tab: "Access Requests"
  sections: ["PENDING", "REVIEWED"]
  empty_states: ["No pending requests", "No reviewed requests yet"]
  approve: "Approve"
  reject: "Reject"
  confirm_title: "Approve access request?"
  reviewed_by: ["Approved", "Rejected", "by WorkspaceAdmin"]
  notification_title: "Access request from <Name>"
  settings_dialog_title: "Request Access: <Module>"
  settings_options: ["Read-only", "Manage / Edit"]
  settings_submit: "Submit Request"
  settings_chip: "Requested"

procedures:
  - id: request-access-to-a-module
    goal: Ask a Workspace Admin for Read or Manage access to one module.
    steps:
      - 'In the sidebar, or in the "Hub" dropdown, select the dimmed module you need.'
      - 'On "Access Restricted", select "Request Access".'
      - 'Select "Read access" or "Manage access".'
      - 'Optional: in "Why do you need this access? (optional)", describe what you need it for.'
      - 'Select "Send request".'
    expect: 'Toast "Access request sent to your admin". The dialog closes and the Access Restricted page is unchanged.'
    verify: 'Team > Access Requests > PENDING contains a card with the requester name and the line "<Permission> · <Module>".'
    on_fail: 'Toast "Failed to send request. Please try again." Return to step 5. "Send request" is disabled until one of the two cards is selected.'
    reversible: false
    undo: 'None in-product. There is no withdraw, edit or expiry. Ask a Workspace Admin to reject it.'
  - id: review-a-request
    goal: Approve or reject a pending access request as a Workspace Admin.
    steps:
      - 'In the sidebar, open the user menu and select "Team".'
      - 'Select the "Access Requests" tab.'
      - 'Under "PENDING", find the request by the person''s name and the line "<Permission> · <Module>".'
      - 'Select "Approve". To decline instead, select "Reject" here - the card moves to "REVIEWED" at once, with no confirmation dialog, and the remaining steps do not apply.'
      - 'In "Approve access request?", read which role the person will be moved onto. If the dialog names no role, the requester has no matching Manage Team record and approving will change no role.'
      - 'Select "Approve".'
    expect: 'Approve - toast "Access granted to <Name>", with description "Created role “<Role>”." or "Assigned existing role “<Role>”." when a Manage Team record matched, and no description when none did. Reject - toast "Request rejected".'
    verify: 'The card sits under REVIEWED reading "Approved by WorkspaceAdmin" or "Rejected by WorkspaceAdmin". After an approval whose toast carried a description, Team > Manage Team shows that member on the new role; a toast with no description means no member record changed.'
    on_fail: 'Toast "Failed to approve request" or "Failed to reject request" means the review did not go through - usually already reviewed elsewhere, but also any API or network failure, such as an unreachable server. Return to step 2 and re-read the list.'
    reversible: false
    undo: 'None in-product. A reviewed request cannot be reopened; ask the person to raise a new request.'

limits:
  - Only two rights are requestable per module - "Read access" and "Manage access". Individual action buttons are never offered.
  - The reason field is optional and has no maximum length.
  - Duplicate requests are allowed - the same person can raise the same module repeatedly and each creates a card.
  - The Access Requests list re-reads the server every 15 seconds and on window focus.
  - The amber tab badge is recalculated on page load and after an approval only, not after a rejection.
  - Every review is recorded as "WorkspaceAdmin" regardless of who performed it.
  - The list has no search, filter, sort, pagination or per-request page.
  - Approving a request whose requester matches no Manage Team record generates no role and changes no member record; the toast then carries no description.
  - Surfaces outside the sidebar and Hub module list - "Generate Report" in the command palette, for example - also render Access Restricted, and the Request Access dialog there offers no options, so "Send request" can never be enabled.

errors:
  - when: The request could not be created
    message: "Failed to send request. Please try again."
    fix: Select "Send request" again.
  - when: The approval call failed - usually the request was already approved or rejected elsewhere, but any API or network failure produces the same toast
    message: "Failed to approve request"
    fix: Re-read Team > Access Requests. A request can be reviewed once. If the card is still pending, check that the backend is reachable.
  - when: The rejection call failed - usually the request was already approved or rejected elsewhere, but any API or network failure produces the same toast
    message: "Failed to reject request"
    fix: Re-read Team > Access Requests. A request can be reviewed once. If the card is still pending, check that the backend is reachable.

agent_rules:
  - Do not tell a requester that an approval grants them the module. Their session role is fixed at sign-in and Access Restricted stays.
  - Do not tell a requester to wait for a notification of the decision. None is sent.
  - Do not name the approving admin. Every review is recorded as "WorkspaceAdmin".
  - Do not treat the Settings > Preferences > Additional Capabilities "Request Access" button as this flow. It creates no request.
  - Do not treat the Support issue type "Access request" as a permission change. It files a Support issue.

related: [roles-and-permissions, manage-your-team, custom-roles, permissions-matrix-reference, whats-live-in-this-build]
```

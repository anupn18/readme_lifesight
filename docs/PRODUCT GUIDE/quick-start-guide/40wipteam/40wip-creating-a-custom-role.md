---
title: '[4.0][WIP] Creating a Custom Role'
excerpt: >-
  Team > Manage Roles holds the five preset roles and the Read, Manage and
  Actions grid where a Workspace Admin creates, edits and deletes custom roles.
deprecated: false
hidden: true
metadata:
  robots: index
---
A custom role is a set of rights you assemble yourself, module by module, on
**Team > Manage Roles** — the tab that also shows the five preset roles read-only.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin. Every role can open the tab and read the grid. For everyone else **New role** stays visible at 50% opacity with the tooltip `Your role ({Role}) cannot create new role. Ask a workspace admin for access.`
  **Where:** Sidebar user menu > **Team** > **Manage Roles**
  **In this build:** This browser — a custom role stays in this tab, never sent to the server. See [What's live in this build](doc:whats-live-in-this-build).
  **Time:** About 3 minutes per role.
</Callout>

## Look at a preset role first

**Manage Roles** opens on **Workspace Admin**.

1. In the sidebar, open the user menu and select **Team**.
2. Select the **Manage Roles** tab.
3. Under **Preset Roles**, select a role.

You should see the role name in the right pane, a **Preset** badge, the tagline, and
the number of rights it holds above the caption **permissions**. A preset is read-only:
no checkboxes, no filter, no footer.

| Preset role             | Tagline                                          | Rights held |
| ----------------------- | ------------------------------------------------ | ----------- |
| **Workspace Admin**     | Full platform access                             | 55 of 55    |
| **Data Practitioner**   | Data pipelines & measurement infrastructure      | 27 of 55    |
| **Marketing Scientist** | Attribution, experiments & creative intelligence | 29 of 55    |
| **Strategic Planner**   | Campaign planning & budget deployment            | 24 of 55    |
| **Executive**           | Read-only strategic overview                     | 16 of 55    |

**Viewer** is a sixth built-in role, not listed here; it is offered in **Change role**
on **Manage Team**. See
[Roles: what each one opens, and what it can do](doc:roles-and-permissions).

Under **Custom Roles**, below the presets, the hint **None yet** shows until you create one.

## Create a custom role

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin (`team.create_new_role`)
</Callout>

1. On **Team > Manage Roles**, select **New role**.
2. In the name field, enter a name for the role.
3. Optional: in **Filter by label or type…**, enter a label, a right code such as `LS-DA-03`, or `read`, `manage` or `action`.
4. Tick **Read** on every module the role should open.
5. Tick **Manage** on every module the role should also change.
6. Select the chips in **Actions** that the role should be able to use.
7. Select **Create role**.

You should see the toast `Role "{name}" saved`, the role under **Custom Roles**, and
the right pane headed by the role name with an **Editing** badge. **Create role** stays
disabled until the name field has text, so a blank name raises `Enter a role name` only
if you press Enter in the empty field. If the toast reads
`A role with that name already exists`, change the name and return to step 7.

The name field carries the placeholder **Custom Role Name**, takes focus on its own,
and saves on Enter. The counter above the grid reads `{n} of 55 permissions selected`
and updates as you tick. **Clear** empties the filter.


<Image src="_assets/SHOT-09-manage-roles-edit-mode.png" alt="Manage Roles with a custom role open in edit mode, showing the Module, Read, Manage and Actions columns, the filter field and the permissions counter" caption="The chips in Actions are picked one at a time." framed={true} />


You're done when:

- ☐ The role appears under **Custom Roles** in the left pane.
- ☐ The counter matches the rights you meant to grant.
- ☐ The role is offered in **Invite User** and **Change role** on **Manage Team**.

<Callout icon="🚧" theme="warn">
  ### A custom role lives in this browser tab

  Custom roles are saved in this tab's sessionStorage. They are never sent to the server, gone when the tab closes, and seen by no one else. Assigning one to a member does not change what that person can open, because a role is fixed at sign-in. See [What's live in this build](doc:whats-live-in-this-build).
</Callout>

## Edit a custom role

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin (`team.edit_permissions`)
</Callout>

You can edit a custom role while no active member holds it. The pencil and trash appear
on hover in the left pane, only on a role with 0 active members.

1. On **Team > Manage Roles**, hover the role under **Custom Roles**.
2. Select the pencil (**Edit role**).
3. Change the ticks and the chips.
4. Select **Save changes**.

You should see the **Editing** badge clear and the grid return to read-only. The footer
reads **Unsaved changes** while your draft differs from the saved role; **Cancel**
discards it.

A role that active members hold shows a **Locked** badge and the banner
`{N} active user(s) assigned — reassign them to edit this role.` Move those people onto
another role on **Manage Team** first — see
[Invite, change, and deactivate teammates](doc:manage-your-team). Members with status
**Pending** or **Expired** do not lock a role; only active ones do.

Editing a role does not re-save permissions for the members already on it.

## Delete a custom role

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin (`team.create_new_role`)
</Callout>

The trash sits beside the pencil, under the same 0-active-members rule.

<Callout icon="❗️" theme="error">
  ### Deleting a role cannot be undone

  The dialog says so: `Are you sure you want to delete "{name}"? This cannot be undone.` No restore: rebuilding the role means ticking every right again. To keep the role and free it up instead, move its members onto another role on **Manage Team**.
</Callout>

1. On **Team > Manage Roles**, hover the role under **Custom Roles**.
2. Select the trash (**Delete role**).
3. In the dialog, select **Delete role**.

You should see the toast `Role deleted` and the role gone from **Custom Roles**. When
the deleted role was open in the right pane, the selection returns to **Workspace
Admin**.

## How the Read, Manage and Actions columns work

The grid has four columns — **Module**, **Read**, **Manage** and **Actions** — and its
rows are grouped under **Platform**, **Action**, **Intelligence**, **Causality**,
**System**, **Artifacts** and **Workspace**. It holds 55 rights: a read and a manage
right for each of the 16 modules, plus one right per action, 23 in all.

| Column      | What it grants                                    | The rule                                                                                                            |
| ----------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Read**    | Opens the module for viewing                      | Unticking **Read** unticks **Manage** on that module                                                                |
| **Manage**  | Changes and configures the module                 | Ticking **Manage** ticks **Read** on that module                                                                    |
| **Actions** | One named button, such as **Connect Integration** | Chips are independent of **Read** and **Manage**, and an action right stays denied while the module has no **Read** |

Nine modules carry action rights: Cockpit 1, Plan 2, Deploy 3, Attribution 2, Models 3,
Experiments 1, Data 4, Team 4 and Settings 3. The other seven — Creative, Agents,
Profiles, Segments, Brain, Config and Artifacts — have none; their **Actions** cell is
always `—`.

Outside edit mode the grid lists only the modules that hold at least one right. A cell
reads `✓` when the right is granted and `—` when it is not, and granted action rights
appear as chips. A custom role with nothing ticked reads `No permissions granted` with
the line `Use the pencil beside this role to add permissions`. A filter that matches
nothing reads `No rights match your search`.

The full role-by-module-by-right matrix is on
[Permissions matrix](doc:permissions-matrix-reference).

## FAQ

### Should I create a custom role or move the person onto a preset?

Move the person onto a preset when one of the five covers their needs — one step on
**Manage Team**. Create a custom role for a combination no preset holds. Neither
persists in this build: a role change is lost on a full page reload, a custom role when
the tab closes.

### Why can't I edit or delete my custom role?

Editing and deleting are blocked while active members hold the role. It shows a
**Locked** badge, the banner names how many members are assigned, and the pencil and
trash do not appear on hover. Move those members onto another role on **Manage Team**,
then hover the role again.

### Where did my custom role go?

A custom role is stored in the browser tab you created it in. Closing that tab, opening
the workspace in a second tab, or signing in on another machine leaves you without it,
and no colleague ever sees it.

### I ticked an action right, so why is the button still dimmed?

An action right is only ever allowed when the same module also has **Read**. In this
build neither tick changes anything for anyone — a custom role's rights are never
applied at sign-in, so the buttons a person sees come from the preset role their
sign-in carries.

### Why is Viewer missing from Preset Roles?

Viewer is not listed under **Preset Roles**, and it is not offered in **Invite User**
either. It is offered in the **Change role** dialog on **Manage Team**, so assign it
there after the person is in the workspace.

## Related

<Cards columns="2">
  <Card title="Roles: what each one opens" href="doc:roles-and-permissions" icon="fa-user-shield">
    The permission model behind the grid, role by role.
  </Card>

  <Card title="Invite, change, and deactivate teammates" href="doc:manage-your-team" icon="fa-user-plus">
    Where a role gets assigned, and where a locked role gets freed.
  </Card>

  <Card title="Ask for access, and review requests" href="doc:access-requests" icon="fa-key">
    The other way a custom role gets created.
  </Card>

  <Card title="Permissions matrix" href="doc:permissions-matrix-reference" icon="fa-table-cells">
    Every role, module and right in one generated table.
  </Card>
</Cards>

## Agent card

```yaml agent
task: team-custom-roles
title: Create a custom role
type: howto
surface: Team
page: https://docs.lifesight.io/docs/custom-roles
last_verified: 2026-09-13
app_build: "ls4x@feature/LS4X-155"

state: browser
persistence: browser_session
state_note: >
  A custom role is written to this browser tab's sessionStorage under the key
  "access_rights_roles_v1". It is never sent to the server, it is gone when the tab
  closes, and no other user or device sees it. Preset roles are read-only and cannot
  be changed. Assigning a custom role to a member does not change what that person
  can open: a session's role is fixed at sign-in.

requires_role: [Workspace Admin]
requires_rights: [team.create_new_role, team.edit_permissions]
denied_ux: >
  Every role can open the "Manage Roles" tab and read the grid. "New role" stays
  visible at 50% opacity with the tooltip "Your role ({Role}) cannot create new role.
  Ask a workspace admin for access." The pencil and trash icons are dimmed and inert
  without the matching right, so the editor and the delete dialog are never reached.

entry_point: "Sidebar user menu > Team > Manage Roles"
url: "/team?tab=roles-v3"
preconditions:
  - Signed in as a Workspace Admin.
  - The Team page is open on the Manage Roles tab.
  - For edit and delete: the custom role has 0 active members assigned.

ui_strings:
  tab: "Manage Roles"
  left_pane: "Roles"
  sections: ["Preset Roles", "Custom Roles"]
  empty_custom_roles: "None yet"
  primary_action: "New role"
  name_placeholder: "Custom Role Name"
  counter: "{n} of 55 permissions selected"
  filter_placeholder: "Filter by label or type…"
  filter_clear: "Clear"
  columns: ["Module", "Read", "Manage", "Actions"]
  row_sections: ["Platform", "Action", "Intelligence", "Causality", "System", "Artifacts", "Workspace"]
  checkbox_labels: ["Toggle Read access", "Toggle Manage access"]
  badges: ["Preset", "Locked", "Editing"]
  row_icons: ["Edit role", "Delete role"]
  footer: ["Unsaved changes", "Cancel", "Create role", "Save changes", "Saving…"]
  delete_dialog_title: "Delete role"
  delete_dialog_body: 'Are you sure you want to delete "{name}"? This cannot be undone.'
  delete_confirm: "Delete role"
  lock_banner: "{N} active user(s) assigned — reassign them to edit this role."
  empty_grid: "No permissions granted"
  empty_filter: "No rights match your search"

procedures:
  - id: look-at-a-preset-role-first
    goal: Read a preset role's rights before deciding to build one.
    steps:
      - 'In the sidebar, open the user menu and select "Team".'
      - 'Select the "Manage Roles" tab.'
      - 'Under "Preset Roles", select a role.'
    expect: 'The right pane shows the role name, a "Preset" badge, the tagline and the rights count above the caption "permissions".'
    verify: 'The grid renders without checkboxes, without the filter field and without a footer.'
    on_fail: 'Return to step 2. The tab strip is on the Team page at "/team".'
    reversible: true
    undo: 'None needed. Reading a preset changes nothing.'
  - id: create-a-custom-role
    goal: Build a new role out of Read, Manage and action rights.
    steps:
      - 'On "Team > Manage Roles", select "New role".'
      - 'In the name field, enter a name for the role.'
      - 'Optional: in "Filter by label or type…", enter a label, a right code such as "LS-DA-03", or "read", "manage" or "action".'
      - 'Tick "Read" on every module the role should open.'
      - 'Tick "Manage" on every module the role should also change.'
      - 'Select the chips in "Actions" that the role should be able to use.'
      - 'Select "Create role".'
    expect: 'Toast "Role "{name}" saved", the role listed under "Custom Roles", and the right pane still headed by the role name with an "Editing" badge beside it.'
    verify: 'The role name is offered in the "Invite User" dialog and in the "Change role" dialog on Manage Team.'
    on_fail: 'Return to step 7. "Create role" is disabled until the name field has text, and a duplicate name raises a toast and saves nothing.'
    reversible: true
    undo: 'Hover the role under "Custom Roles", select the trash ("Delete role"), then select "Delete role".'
  - id: edit-a-custom-role
    goal: Change the rights on a custom role that nobody active holds.
    steps:
      - 'On "Team > Manage Roles", hover the role under "Custom Roles".'
      - 'Select the pencil ("Edit role").'
      - 'Change the ticks and the chips.'
      - 'Select "Save changes".'
    expect: 'Toast "Role "{name}" saved" and the grid back in read-only view.'
    verify: 'The "Editing" badge is gone and the rights count matches the new selection.'
    on_fail: 'Return to step 1. The pencil does not appear on a role with active members.'
    reversible: true
    undo: 'Edit the role again and restore the previous ticks. "Cancel" discards an unsaved draft.'
  - id: delete-a-custom-role
    goal: Remove a custom role from the workspace.
    steps:
      - 'On "Team > Manage Roles", hover the role under "Custom Roles".'
      - 'Select the trash ("Delete role").'
      - 'In the dialog, select "Delete role".'
    expect: 'Toast "Role deleted" and the role removed from "Custom Roles".'
    verify: 'The left pane no longer lists the role, and the right pane shows Workspace Admin when the deleted role was selected.'
    on_fail: 'Return to step 1. The trash does not appear on a role with active members.'
    reversible: false
    undo: 'None. Create the role again and tick every right a second time.'

limits:
  - The grid holds 55 rights: a read and a manage right for each of the 16 modules, plus one right per action, 23 in all.
  - Action rights exist for 9 modules only — Cockpit 1, Plan 2, Deploy 3, Attribution 2, Models 3, Experiments 1, Data 4, Team 4, Settings 3.
  - Preset rights counts are Workspace Admin 55, Data Practitioner 27, Marketing Scientist 29, Strategic Planner 24, Executive 16.
  - Viewer is not listed under "Preset Roles" and is not offered in "Invite User".
  - Role names are trimmed and compared case-sensitively against the five internal preset keys (WorkspaceAdmin, DataPractitioner, MarketingScientist, StrategicPlanner, Executive) and existing custom names — so the spaced forms, and Viewer, are accepted. There is no length limit.
  - Only members with status active lock a role; invited and expired members do not.
  - Manage Roles opens on Workspace Admin and returns to it after a delete or a cancelled create.

errors:
  - when: Enter is pressed in an empty name field — "Create role" itself stays disabled until the field has text
    message: "Enter a role name"
    fix: Enter a name in the field, then select "Create role".
  - when: The name matches a preset key or an existing custom role name
    message: "A role with that name already exists"
    fix: Enter a different name, then select "Create role" again.

agent_rules:
  - Do not report a custom role as saved for the workspace. It lives in one browser tab and is never sent to the server.
  - Do not tell the user that assigning a custom role changes what that person can open. A role is fixed at sign-in.
  - Do not offer Viewer under "Preset Roles". It is listed only in the "Change role" dialog on Manage Team.
  - Do not give a procedure for editing or deleting a role that has active members. The pencil and trash do not appear on it.
  - Do not promise that an action right works on its own. The same module also needs "Read".

related: [roles-and-permissions, manage-your-team, access-requests, permissions-matrix-reference, whats-live-in-this-build]
```
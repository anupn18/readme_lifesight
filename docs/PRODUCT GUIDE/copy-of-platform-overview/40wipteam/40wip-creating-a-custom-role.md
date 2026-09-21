---
title: '[4.0][ReadyForQA] Creating a Custom Role'
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
  **Time:** About 3 minutes per role.
</Callout>

## Look at a preset role first

**Manage Roles** opens on **Workspace Admin**.

1. In the sidebar, open the user menu and select **Team**.
2. Select the **Manage Roles** tab.
3. Under **Preset Roles**, select a role.

You should see the role name in the right pane, the tagline, and the number of rights it holds above the caption **permissions**. A preset is read-only: no checkboxes, no filter, no footer.

| Preset role             | Tagline                                          | Rights held |
| ----------------------- | ------------------------------------------------ | ----------- |
| **Workspace Admin**     | Full platform access                             | 55 of 55    |
| **Data Practitioner**   | Data pipelines & measurement infrastructure      | 27 of 55    |
| **Marketing Scientist** | Attribution, experiments & creative intelligence | 29 of 55    |
| **Strategic Planner**   | Campaign planning & budget deployment            | 24 of 55    |
| **Executive**           | Read-only strategic overview                     | 16 of 55    |

**Viewer** is a sixth built-in role. See [Roles: what each one opens, and what it can do](doc:roles-and-permissions). Under **Custom Roles**, below the presets, the hint **None yet** shows until you create one.

## Create a custom role

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin
</Callout>

1. On **Team > Manage Roles**, select **New role**.
2. In the name field, enter a name for the role.
3. Optional: in **Filter by label or type…**, enter a label, a right code such as `LS-DA-03`, or `read`, `manage` or `action`.
4. Tick **Read** on every module the role should open.
5. Tick **Manage** on every module the role should also change.
6. Select the chips in **Actions** that the role should be able to use.
7. Select **Create role**.

You should see the toast `Role "{name}" saved`, the role under **Custom Roles**, and the right pane headed by the role name with an **Editing** badge. **Create role** stays disabled until the name field has text, so a blank name raises `Enter a role name` only if you press Enter in the empty field. If the toast reads `A role with that name already exists`, change the name and return to step 7.

The name field carries the placeholder **Custom Role Name**, takes focus on its own,
and saves on Enter. The counter above the grid reads `{n} of 55 permissions selected`
and updates as you tick. **Clear** empties the filter.

You're done when:

- The role appears under **Custom Roles** in the left pane.
- The counter matches the rights you meant to grant.
- The role is offered in **Invite User** and **Change role** on **Manage Team**.

## &#x20;the Read, Manage and Actions columns work

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

The full role-by-module-by-right matrix is on [Permissions matrix](doc:permissions-matrix-reference).

## FAQ

### Should I create a custom role or move the person onto a preset?

Move the person onto a preset when one of the five covers their needs — one step on **Manage Team**. Create a custom role for a combination no preset holds.

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

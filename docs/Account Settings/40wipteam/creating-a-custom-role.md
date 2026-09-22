---
title: Create a custom role
excerpt: >-
  Team > Manage Roles holds the five preset roles and the Read, Manage and
  Actions grid where a Workspace Admin creates, edits and deletes custom roles.
deprecated: false
hidden: true
metadata:
  title: Create a custom role in Lifesight
  keywords:
    - Lifesight custom role
  robots: index
---
A role decides what a person can open and change in Lifesight. Five preset roles cover most teams, but when someone needs a combination no preset holds, you build a custom role: a set of rights you assemble yourself, module by module.

Everything happens on **Team > Manage Roles**, the tab that also shows the five preset roles read-only. Start by reading a preset that comes close to what you need, so you can see the shape you are aiming for before you tick anything.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin. Every role can open the tab and read the grid. For everyone else **New role** stays visible at 50% opacity with the tooltip `Your role ({Role}) cannot create new role. Ask a workspace admin for access.`<br />**Where:** Sidebar user menu > **Team** > **Manage Roles**<br />**Time:** About 3 minutes per role.
</Callout>

## Before you start

- You are signed in as a Workspace Admin.
- Team > Manage Roles is open.
- You know which modules the person needs to open, which they need to change, and which named actions they need to run.
- You have checked whether a preset already covers it. Moving someone onto a preset is one step on Manage Team.

## Read a preset role first

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

1. In **Team > Manage Roles**, select **New role**.
2. In the name field, enter a name for the role.
3. Optional: in **Filter by label or type…**, enter a label, a right code such as `LS-DA-03`, or `read`, `manage` or `action`.
4. Tick **Read** on every module the role should open.
5. Tick **Manage** on every module the role should also change.
6. Select the chips in **Actions** that the role should be able to use.
7. Select **Create role**.

![](https://files.readme.io/b18963e9a4a0b23866d951c7bad65b1d9bbf0c19f590bbed1b778316f90b204b-Screenshot_2026-09-21_at_7.58.35_AM.png)

<br />You should see the toast `Role "{name}" saved`, the role under **Custom Roles**, and the right pane headed by the role name with an **Editing** badge.&#x20;

**Create role** stays disabled until the name field has text, so a blank name raises `Enter a role name` only if you press Enter in the empty field. If the toast reads `A role with that name already exists`, change the name and return to step 7.

You're done when:

- The role appears under **Custom Roles** in the left pane.
- The counter matches the rights you meant to grant.
- The role is offered in **Invite User** and **Change role** on **Manage Team**.

## Understand the Read, Manage, and Actions columns

The grid has four columns, Module, Read, Manage, and Actions, with rows grouped under Platform, Action, Intelligence, Causality, System, Artifacts, and Workspace.

It holds 55 rights in total: a read and a manage right for each of the 16 modules, plus one right per action, 23 in all..

| Column      | What it grants                                    | The rule                                                                                                            |
| ----------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Read**    | Opens the module for viewing                      | Unticking **Read** unticks **Manage** on that module                                                                |
| **Manage**  | Changes and configures the module                 | Ticking **Manage** ticks **Read** on that module                                                                    |
| **Actions** | One named button, such as **Connect Integration** | Chips are independent of **Read** and **Manage**, and an action right stays denied while the module has no **Read** |

Because of that last rule, always grant Read on a module before you select its action chips. An action chip on a module with no Read grants nothing.

**Which modules carry actions:** Nine do: Cockpit 1, Plan 2, Deploy 3, Attribution 2, Models 3, Experiments 1, Data 4, Team 4, and Settings 3. The other seven, Creative, Agents, Profiles, Segments, Brain, Config, and Artifacts, have none, and their Actions cell always reads `—`

Outside edit mode the grid lists only the modules that hold at least one right. A cell reads ✓ when the right is granted and when it is not, and granted action rights appear as chips. A custom role with nothing ticked reads `No permissions granted` with the line `Use the pencil beside this role to add permissions`. A filter that matches nothing reads No rights match your search.

The full role-by-module-by-right matrix is on [Permissions matrix](doc:permissions-matrix-reference).

## FAQ

**Should I create a custom role or move the person onto a preset?**

Move the person onto a preset when one of the five covers their needs, which is one step on Manage Team. Create a custom role for a combination no preset holds.

**Should I create a custom role or move the person onto a preset?**

Move the person onto a preset when one of the five covers their needs, which is one step on Manage Team. Create a custom role for a combination no preset holds.

**How many rights are there in total?**

55: a read and a manage right for each of the 16 modules, plus 23 action rights spread across nine modules.

**Why did Read tick itself when I ticked Manage?**

You cannot change a module you cannot open, so Manage always carries Read with it. The reverse also holds: removing Read removes Manage.

**Can I grant an action without granting the module?**

You can tick the chip, but it will not work. An action right stays denied while the module has no Read.

**Where does the role get used?**

Once saved, it appears in Invite User and Change role on Manage Team. See Invite, change, and deactivate teammates.

**Can I create a custom role from the invite dialog?**

No. Selecting + Create Custom Role there sends you here. Build the role first, then invite.

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
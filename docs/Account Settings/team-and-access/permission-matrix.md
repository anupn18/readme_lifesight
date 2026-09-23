---
title: Permission Matrix
excerpt: The generated grid of six Lifesight roles.
deprecated: false
hidden: true
metadata:
  title: Permission Matrix
  robots: index
---
## How to read this matrix

This matrix shows what every role in Lifesight can open and change, module by module. Use it to check what a teammate will be able to do before you invite them or change their role, to spot where a preset role falls short and a custom role is needed, or to understand why a module shows **Access Restricted** for someone on your team.

Every cell in the tables below uses one of three symbols, so once you know them you can read any table on this page at a glance.

**Legend:** ● Manage (full) · ◐ Read · ○ No access (grayed out in the sidebar, opens Access Restricted)

**In the per-module tables**, each symbol matches a value in the source grid:

● is F: the role can read and has full access.
◐ is R: the role can read only.
○ is N: the role has neither.

**In the module-level table,** the symbols summarize the whole module:

● means the role holds Manage access on at least one non-action sub-module.
◐ means the module opens, but without Manage access.
○ means the module does not open at all.

Role columns in the per-module tables are abbreviated to save space. The table below maps each abbreviation to its full role name and its role key.

| Abbreviation | Role                | Role key in code     |
| ------------ | ------------------- | -------------------- |
| WA           | Workspace Admin     | `WorkspaceAdmin`     |
| DP           | Data Practitioner   | `DataPractitioner`   |
| MS           | Marketing Scientist | `MarketingScientist` |
| SP           | Strategic Planner   | `StrategicPlanner`   |
| EX           | Executive           | `Executive`          |
| VW           | Viewer              | `Viewer`             |

Two rules turn a cell into behaviour, and both are evaluated in the browser as the
page renders.

| Rule                 | What it decides                                            | How it is evaluated                                                                                                                                               |
| -------------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Module opens         | Whether the module renders, or shows **Access Restricted** | The module opens when at least one of its sub-modules carries read. Action sub-modules count, because a granted action carries read as well                       |
| Action right allowed | Whether one named button responds                          | The button works when its module opens and the action key itself carries `fullAccess`. An unlisted key is denied, and `read` on an action key is an explicit deny |

**Settings, Team, and Support** open for every role. Only the buttons inside them are limited by role. Support is always open. Settings and Team open because every role includes read access to notification preferences and to the team member list. A custom or unrecognized role with no rights set up still opens both. That is wh&#x79;**&#x20;Settings and Team** still appear as rows in the tables below.

This page describes rights, not people. Your session carries the role it was given when you signed in, based on the email address you signed in with, and that role does not change until you sign in again. See [Sign in, stay signed in, and log out](doc:sign-in).

## Roles

Six roles ship built in. The lookup key is the role name as the product writes it.

| Role                    | Key                  | Tagline                                          |
| ----------------------- | -------------------- | ------------------------------------------------ |
| **Workspace Admin**     | `WorkspaceAdmin`     | Full platform access                             |
| **Data Practitioner**   | `DataPractitioner`   | Data pipelines & measurement infrastructure      |
| **Marketing Scientist** | `MarketingScientist` | Attribution, experiments & creative intelligence |
| **Strategic Planner**   | `StrategicPlanner`   | Campaign planning & budget deployment            |
| **Executive**           | `Executive`          | Read-only strategic overview                     |
| **Viewer**              | `Viewer`             | Read-only across every module                    |

**Lifesight has 55 rights in total.** Each of the 16 modules has a **Read access** right and a **Manage access** right, and each of the 23 actions has one right of its own. When you select a role on **Manage Roles,** the detail panel shows how many rights it holds, as a number labeled permissions. Viewer does not appear on **Manage Roles or in the Invite User role** list, so its count of 16 comes from the same grid rather than from a screen.

**Viewer and Executive both hold 16 rights, but not the same 16.** Viewer can read all 16 modules and holds no action rights. Executive opens four fewer modules and holds three action rights.

**Older role names map to current ones**. admin becomes `WorkspaceAdmin`, `analyst `becomes `Data Practitioner`, executive becomes` Executive`, and viewer becomes `Viewer.`

## Module access by role

Every Lifesight module appears here, one per row, so you can check what each role can open or manage, including modules that don't have their own article in this guide.

**Legend:** ● Manage (full) · ◐ Read · ○ No access (greyed sidebar, Access Restricted)

| Module          | Workspace Admin | Data Practitioner | Marketing Scientist | Strategic Planner | Executive | Viewer |
| --------------- | --------------- | ----------------- | ------------------- | ----------------- | --------- | ------ |
| **Cockpit**     | ●               | ◐                 | ◐                   | ◐                 | ◐         | ◐      |
| **Plan**        | ●               | ◐                 | ◐                   | ●                 | ◐         | ◐      |
| **Deploy**      | ●               | ◐                 | ◐                   | ◐                 | ◐         | ◐      |
| **Attribution** | ●               | ●                 | ●                   | ◐                 | ◐         | ◐      |
| **Creative**    | ●               | ◐                 | ●                   | ◐                 | ◐         | ◐      |
| **Models**      | ●               | ●                 | ◐                   | ◐                 | ◐         | ◐      |
| **Experiments** | ●               | ●                 | ●                   | ◐                 | ◐         | ◐      |
| **Agents**      | ●               | ◐                 | ◐                   | ◐                 | ◐         | ◐      |
| **Profiles**    | ●               | ◐                 | ◐                   | ○                 | ○         | ◐      |
| **Segments**    | ●               | ●                 | ◐                   | ◐                 | ○         | ◐      |
| **Data**        | ●               | ●                 | ◐                   | ○                 | ○         | ◐      |
| **Brain**       | ●               | ◐                 | ◐                   | ◐                 | ◐         | ◐      |
| **Config**      | ●               | ○                 | ○                   | ○                 | ○         | ◐      |
| **Artifacts**   | ●               | ◐                 | ◐                   | ●                 | ◐         | ◐      |
| **Team**        | ●               | ◐                 | ◐                   | ◐                 | ◐         | ◐      |
| **Settings**    | ●               | ●                 | ●                   | ●                 | ●         | ◐      |

**A ○ cell is what sends someone to Access Restricted,** where they can select **Request Access**. See

[Ask for access, and review requests](doc:access-requests).

**Marketing Scientist can open Data without Read access on it.** Two of the action rights the role holds include read, so the module opens, and the table shows ◐. Every other part of Data stays ○ for that role.

## Sub-modules and action rights by role

**The tables below go module by module, in the same order&#x20;**&#x74;he modules appear on Manage Roles. Within each table, the module's regular rights come first, followed by its action rights.

**Rows marked · action are action rights**. Each one controls a specific button in the product. The key on each action row is the same right code used in the agent cards across these pages.

**Legend:** ● F full access · ◐ R read only · ○ N no access. On a · action row, ● means the button works for that role, and both ◐ and ○ mean it does not.

[Cockpit](#cockpit) · [Plan](#plan) · [Deploy](#deploy) · [Attribution](#attribution) · [Creative](#creative) · [Models](#models) · [Experiments](#experiments) · [Data](#data) · [Config](#config) · [Artifacts](#artifacts) · [Team](#team) · [Settings](#settings)

### Cockpit

**Manage Roles** groups **Cockpit** under **Platform**. The module page is `/cockpit` and it carries 1 action right.

| Sub-module                                 | WA | DP | MS | SP | EX | VW |
| ------------------------------------------ | -- | -- | -- | -- | -- | -- |
| **Overview & KPIs**                        | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Recommendations**                        | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Alert configuration**                    | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Publish Artifact from Cockpit** · action | ●  | ○  | ○  | ●  | ●  | ○  |

### Plan

**Manage Roles** groups **Plan** under **Action**. The module page is `/planning`, and it carries 2 action rights.

| Sub-module                                | WA | DP | MS | SP | EX | VW |
| ----------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Scenario workspace**                    | ●  | ◐  | ◐  | ●  | ◐  | ◐  |
| **Budget simulation**                     | ●  | ◐  | ◐  | ●  | ○  | ◐  |
| **Export plans**                          | ●  | ◐  | ○  | ●  | ○  | ◐  |
| **Run Simulation**                        | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Promote to Decision** · action          | ●  | ○  | ○  | ●  | ●  | ○  |
| **Download / Export Allocation** · action | ●  | ○  | ●  | ●  | ●  | ○  |

### Deploy

**Manage Roles** groups **Deploy** under **Action**. The module page is `/decisions`, and it carries 3 action rights.

| Sub-module                     | WA | DP | MS | SP | EX | VW |
| ------------------------------ | -- | -- | -- | -- | -- | -- |
| **Decision queue**             | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Review & approve**           | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Activity log**               | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Change bid**                 | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Budget**                     | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Change Bid/Budget** · action | ●  | ○  | ●  | ●  | ○  | ○  |
| **Change Status** · action     | ●  | ○  | ●  | ●  | ○  | ○  |
| **Edit Geo Deploy** · action   | ●  | ○  | ●  | ●  | ○  | ○  |

### Attribution

**Manage Roles** groups **Attribution** under **Intelligence**. The module page is `/attribution`, and it carries 2 action rights.

| Sub-module                                    | WA | DP | MS | SP | EX | VW |
| --------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Channel overview**                          | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Attribution rules**                         | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Conversion events**                         | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Revenue mapping**                           | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Scheduled reports**                         | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Data exports**                              | ●  | ○  | ◐  | ○  | ○  | ◐  |
| **Promote a model from Attribution** · action | ●  | ○  | ●  | ●  | ○  | ○  |
| **Set Benchmark** · action                    | ●  | ○  | ●  | ●  | ○  | ○  |

### Creative

**Manage Roles** groups **Creative** under **Intelligence**. The module page is `creatives`and it carries no action rights.

| Sub-module              | WA | DP | MS | SP | EX | VW |
| ----------------------- | -- | -- | -- | -- | -- | -- |
| **Creative library**    | ●  | ◐  | ●  | ◐  | ○  | ◐  |
| **Performance scoring** | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Tag taxonomy**        | ●  | ○  | ●  | ○  | ○  | ◐  |
| **Brand safety rules**  | ●  | ○  | ○  | ○  | ○  | ◐  |

### Models

**Manage Roles** groups **Models** under **Causality**. The module page is `/models`, and it carries 3 action rights.

| Sub-module                    | WA | DP | MS | SP | EX | VW |
| ----------------------------- | -- | -- | -- | -- | -- | -- |
| **Model registry**            | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Model runs**                | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Budget allocations**        | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Scenario library**          | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Diagnostics**               | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Export results**            | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Create / Update**           | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Merge model**               | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Refresh model**             | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Archive Model**             | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Request rollback** · action | ●  | ●  | ○  | ○  | ○  | ○  |
| **Re-train** · action         | ●  | ○  | ●  | ○  | ○  | ○  |
| **Refresh** · action          | ●  | ○  | ●  | ○  | ○  | ○  |

### Experiments

**Manage Roles** groups **Experiments** under **Causality**. The module page is `/experiments`, and it carries 1 action right.

| Sub-module                      | WA | DP | MS | SP | EX | VW |
| ------------------------------- | -- | -- | -- | -- | -- | -- |
| **Experiment builder**          | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Test library**                | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Results dashboard**           | ●  | ●  | ●  | ◐  | ◐  | ◐  |
| **Holdout groups**              | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Promote experiment** · action | ●  | ●  | ●  | ○  | ○  | ○  |

### Data

**Manage Roles** groups **Data** under **System**. The module page is `/data` and it carries 4 action rights.

| Sub-module                            | WA | DP | MS | SP | EX | VW |
| ------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Integrations**                      | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Transformation rules**              | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Taxonomy management**               | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Pipeline config**                   | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Schema editor**                     | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Data quality monitor**              | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Connect Integration** · action      | ●  | ●  | ●  | ○  | ○  | ○  |
| **Delete Integration** · action       | ●  | ●  | ○  | ○  | ○  | ○  |
| **Edit / Delete Data Model** · action | ●  | ●  | ○  | ○  | ○  | ○  |
| **Add Tactic Mapping** · action       | ●  | ●  | ●  | ○  | ○  | ○  |

### Config

**Manage Roles** groups **Config** under **System**. The module page is `/config` and it carries no action rights.

| Sub-module                                              | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Cost configuration** `config.cost_config`             | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Value settings (AOV & CLTV)** `config.value_settings` | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Keyword configuration** `config.keyword_config`       | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Algorithmic weights** `config.algorithmic_weights`    | ●  | ○  | ○  | ○  | ○  | ◐  |

### Artifacts

**Manage Roles** groups **Artifacts** under **Artifacts**. The module page is `/artifacts` and it carries no action rights.

| Sub-module           | WA | DP | MS | SP | EX | VW |
| -------------------- | -- | -- | -- | -- | -- | -- |
| **Artifact library** | ●  | ◐  | ◐  | ●  | ◐  | ◐  |
| **Template builder** | ●  | ○  | ◐  | ●  | ○  | ◐  |
| **Publish settings** | ●  | ○  | ○  | ○  | ○  | ◐  |

### Team

**Manage Roles** groups **Team** under **Workspace**. The module page is `/team`and it carries 4 action rights.

| Sub-module                    | WA | DP | MS | SP | EX | VW |
| ----------------------------- | -- | -- | -- | -- | -- | -- |
| **View team members**         | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Add / deactivate members**  | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Edit member permissions**   | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Add Users** · action        | ●  | ○  | ○  | ○  | ○  | ○  |
| **Edit Permissions** · action | ●  | ○  | ○  | ○  | ○  | ○  |
| **Create New Role** · action  | ●  | ○  | ○  | ○  | ○  | ○  |
| **Deactivate User** · action  | ●  | ○  | ○  | ○  | ○  | ○  |

Team opens for every role at **View team members**. The four action rights are what separate a Workspace Admin from everyone else.

### Settings

**Manage Roles** groups **Settings** under **Workspace**. The module page is `/settings`, and it carries 3 action rights.

| Sub-module                              | WA | DP | MS | SP | EX | VW |
| --------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Workspace configuration**             | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Notification preferences**            | ●  | ●  | ●  | ●  | ●  | ◐  |
| **API keys & webhooks**                 | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Configure Brand Kit** · action        | ●  | ○  | ○  | ○  | ○  | ○  |
| **Create New Brand Workspace** · action | ●  | ○  | ○  | ○  | ○  | ○  |
| **Update Workspace Settings** · action  | ●  | ○  | ○  | ○  | ○  | ○  |

**Notification preferences** is the one Settings sub-module every role can change, which is why Settings reads ● for five of the six roles.

## Custom roles

The tables on this page cover the six built-in roles only, not custom roles. A custom role is built from the same 55 rights, but the rights it holds are saved in your browser rather than in the tables here. There are two ways a custom role gets created.

| How it is created                            | Where                                    | The name                              |
| -------------------------------------------- | ---------------------------------------- | ------------------------------------- |
| A Workspace Admin builds it                  | **Team > Manage Roles** > **New role**   | Whatever is typed in the name field   |
| A Workspace Admin approves an access request | **Team > Access Requests** > **Approve** | Generated as `{Base role} + {Module}` |

**How a generated role gets its name.&#x20;**&#x57;hen an access request is approved, the new role is named after the role the person already holds, followed by each module they were granted, joined by +. For example, Executive granted Data becomes Executive + Data. A second approval for the same person extends that name, as in Executive + Data + Config. A Workspace Admin never gets a generated role, because they already have access to everything.

**A generated role may not match this page exactly.&#x20;**&#x54;he modules it carries over from the person's original role come from a separate, older list of role access, not from the tables on this page, so the two can differ.

**Custom roles and action buttons.** Treat any role not listed in the table above as holding none of the rights on this page. In this build, action buttons are never enabled for a custom role, so every action right is denied for it. Building one is on [Create a custom role](doc:custom-roles).

***

## Frequently Asked Questions<br />

**What do the symbols in the tables mean?**
● means Manage (full access), ◐ means Read only, and ○ means no access. A ○ module is grayed out in the sidebar and opens **Access Restricted**.

**On an action row, what does ◐ mean?**
The button does not work. On a row marked · action, only ● means the button works. Both ◐ and ○ mean it does not.

**How many rights does Lifesight have in total?**
55: a Read access right and a Manage access right for each of the 16 modules, plus one right for each of the 23 actions.

**Why does a module open for a role that has no Read access on it?**
A module opens when at least one of its sub-modules carries read, and action rights include read. For example, Marketing Scientist can open Data because two of its action rights carry read, even though every other part of Data stays ○ for that role.

**Why do Settings, Team, and Support open for every role?**
Support is always open. Settings and Team open because every role includes read access to notification preferences and to the team member list. Only the buttons inside them are limited by role.

**Viewer and Executive both hold 16 rights. Are they the same?**
No. Viewer can read all 16 modules and holds no action rights. Executive opens four fewer modules but holds three action rights.

**Why doesn't Viewer appear in Manage Roles or the Invite User list?**
Viewer is a built-in role that isn't offered in those lists. Its count of 16 rights comes from the permissions grid rather than from a screen.

**What happens when someone hits a ○ module?**
They see **Access Restricted**, where they can select **Request Access**. See **Ask for access, and review requests**.

**Are custom roles covered on this page?**
No. This page covers the six built-in roles only. A custom role is built from the same 55 rights, but the rights it holds are saved in your browser rather than in these tables.

**Why doesn't my custom role match this page?**
A role generated by approving an access request carries over modules from a separate, older list of role access rather than from these tables, so the two can differ.

**Do action buttons work for a custom role?**
In the current release, action buttons are never enabled for a custom role, so every action right is denied for it. See **Create a custom role**.

**I was given a new role but nothing changed. Why?**
Your session carries the role it was given when you signed in, based on the email address you signed in with. That role doesn't change until you sign in again. See **Sign in, stay signed in, and log out**.

**What do the older role names map to?**
admin becomes WorkspaceAdmin, analyst becomes DataPractitioner, executive becomes Executive, and viewer becomes Viewer.

## Related

<Cards columns="2">
  <Card title="Roles: what each one opens" href="doc:roles-and-permissions" icon="fa-user-shield">
    The model behind this grid, and the six role cards.
  </Card>

  <Card title="Create a custom role" href="doc:custom-roles" icon="fa-user-pen">
    The Read, Manage and Actions grid a Workspace Admin edits.
  </Card>
</Cards>

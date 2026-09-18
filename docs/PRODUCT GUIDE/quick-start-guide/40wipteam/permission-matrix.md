---
title: '[4.0][ReadyForQA]Permission Matrix'
excerpt: >-
  The generated grid of six Lifesight roles against 16 modules, 89 sub-modules
  and 23 action rights, plus one JSON block for validating requires_rights.
deprecated: false
hidden: true
metadata:
  robots: index
---
## How to read this matrix

Three glyphs carry every cell in every table below.

**Legend:** ● Manage (full) · ◐ Read · ○ No access (greyed sidebar, Access Restricted)

In the per-module tables the glyph is the literal value in the source grid: ● is
`F` (`read` and `fullAccess`), ◐ is `R` (`read` only), ○ is `N` (neither). In the
module-level table ● means the role holds Manage access on at least one non-action
sub-module, ◐ means the module opens without it, and ○ means the module does not
open at all.

Role columns in the per-module tables are abbreviated. The table below maps each
abbreviation to its role and to the role key the code looks up.

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

**Settings**, **Team** and **Support** open for every role, and only the buttons
inside them are gated. **Support** (`/help-center`) is hard-coded open. **Settings**
(`/settings`) and **Team** (`/team`) open because every role grid carries read on
`settings.notification_prefs` and `team.view_members`; the hard-coded fallback for
those two only applies to a role with no grid at all (a custom or unrecognised role
name). That is why both still appear as rows below.

This page describes rights, not people. A session carries the role it was issued at
sign-in, from the email address signed in with, and nothing changes that role while
the session lasts — see [Sign in, stay signed in, and log out](doc:sign-in).

## Roles

Six roles ship built in. The lookup key is the role name as the product writes it.

| Role                    | Key                  | Tagline                                          | Rights held | Offered in                                         |
| ----------------------- | -------------------- | ------------------------------------------------ | ----------- | -------------------------------------------------- |
| **Workspace Admin**     | `WorkspaceAdmin`     | Full platform access                             | 55 of 55    | **Invite User**, **Change role**, **Manage Roles** |
| **Data Practitioner**   | `DataPractitioner`   | Data pipelines & measurement infrastructure      | 27 of 55    | **Invite User**, **Change role**, **Manage Roles** |
| **Marketing Scientist** | `MarketingScientist` | Attribution, experiments & creative intelligence | 29 of 55    | **Invite User**, **Change role**, **Manage Roles** |
| **Strategic Planner**   | `StrategicPlanner`   | Campaign planning & budget deployment            | 24 of 55    | **Invite User**, **Change role**, **Manage Roles** |
| **Executive**           | `Executive`          | Read-only strategic overview                     | 16 of 55    | **Invite User**, **Change role**, **Manage Roles** |
| **Viewer**              | `Viewer`             | Read-only across every module                    | 16 of 55    | **Change role**                                    |

There are 55 rights in total. Each of the 16 modules carries a **Read access**
right and a **Manage access** right, and each of the 23 actions carries one right of
its own. **Manage Roles** prints the count in the detail panel when you select a
role — a bare number labelled _permissions_. Viewer is absent from **Manage Roles**
and from the **Invite User** role list, so its 16 is computed from the same grid
rather than read off a screen.

Viewer and Executive both hold 16 rights, and they are not the same 16. Viewer holds
read on all 16 modules and no action right at all. Executive holds four fewer
modules and three action rights.

Legacy role values normalise before any lookup: `admin` resolves to
`WorkspaceAdmin`, `analyst` to `DataPractitioner`, `executive` to `Executive` and
`viewer` to `Viewer`.

## Module access by role

One row per module, including every module this guide does not otherwise document.

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

**Config** is the only module closed to four of the six roles. **Brain** has no
sidebar entry in this build, and `/brain` still routes and is still checked against
the grid. **Visits** is the reverse case: it appears as a sidebar module but carries
no row in this grid in this build, so it is not one of the 16 modules counted here. A
○ cell is what sends a person to **Access Restricted** with **Request Access** on it —
see [Ask for access, and review requests](doc:access-requests).

Marketing Scientist reads ◐ on **Data** without holding **Read access** on it: the
module opens because two granted action rights carry read. Every non-action Data
sub-module is ○ for that role.

## Sub-modules and action rights by role

One table per module, in the order **Manage Roles** renders the modules. Inside a
table the non-action sub-modules come first in registry order, then the action
rights in registry order. Rows marked `· action` are the action rights that gate a
named button, and their keys are the values an agent card's `requires_rights` list
may use.

**Legend:** ● `F` fullAccess · ◐ `R` read only · ○ `N` neither. On a `· action` row,
● is the button enabled, and both ◐ and ○ deny it.

[Cockpit](#cockpit) · [Plan](#plan) · [Deploy](#deploy) · [Attribution](#attribution) · [Creative](#creative) · [Models](#models) · [Experiments](#experiments) · [Agents](#agents) · [Profiles](#profiles) · [Segments](#segments) · [Data](#data) · [Brain](#brain) · [Config](#config) · [Artifacts](#artifacts) · [Team](#team) · [Settings](#settings)

### Cockpit

**Manage Roles** groups **Cockpit** under **Platform**. The module page is `/cockpit`, its module-level rights are `LS-CK-01` and `LS-CK-02`, and it carries 1 action right.

| Sub-module                                                            | WA | DP | MS | SP | EX | VW |
| --------------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Overview & KPIs** `cockpit.overview_dashboard`                      | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Recommendations** `cockpit.recommendations`                         | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Alert configuration** `cockpit.alerts_config`                       | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Publish Artifact from Cockpit** `cockpit.publish_artifact` · action | ●  | ○  | ○  | ●  | ●  | ○  |

### Plan

**Manage Roles** groups **Plan** under **Action**. The module page is `/planning`, its module-level rights are `LS-PL-01` and `LS-PL-02`, and it carries 2 action rights.

| Sub-module                                                                  | WA | DP | MS | SP | EX | VW |
| --------------------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Scenario workspace** `plan.scenario_workspace`                            | ●  | ◐  | ◐  | ●  | ◐  | ◐  |
| **Budget simulation** `plan.budget_simulation`                              | ●  | ◐  | ◐  | ●  | ○  | ◐  |
| **Export plans** `plan.export_plans`                                        | ●  | ◐  | ○  | ●  | ○  | ◐  |
| **Run Simulation** `plan.run_simulation`                                    | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Promote to Decision** `plan.promote_to_decision` · action                 | ●  | ○  | ○  | ●  | ●  | ○  |
| **Download / Export Allocation** `plan.download_export_allocation` · action | ●  | ○  | ●  | ●  | ●  | ○  |

### Deploy

**Manage Roles** groups **Deploy** under **Action**. The module page is `/decisions`, its module-level rights are `LS-DP-01` and `LS-DP-02`, and it carries 3 action rights.

| Sub-module                                                | WA | DP | MS | SP | EX | VW |
| --------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Decision queue** `deploy.decision_queue`                | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Review & approve** `deploy.review_approve`              | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Activity log** `deploy.activity_log`                    | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Change bid** `deploy.change_bid`                        | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Budget** `deploy.budget`                                | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Change Bid/Budget** `deploy.change_bid_budget` · action | ●  | ○  | ●  | ●  | ○  | ○  |
| **Change Status** `deploy.change_status` · action         | ●  | ○  | ●  | ●  | ○  | ○  |
| **Edit Geo Deploy** `deploy.edit_geo_deploy` · action     | ●  | ○  | ●  | ●  | ○  | ○  |

### Attribution

**Manage Roles** groups **Attribution** under **Intelligence**. The module page is `/attribution`, its module-level rights are `LS-AT-01` and `LS-AT-02`, and it carries 2 action rights.

| Sub-module                                                                | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Channel overview** `attribution.channel_overview`                       | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Attribution rules** `attribution.attribution_rules`                     | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Conversion events** `attribution.conversion_events`                     | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Revenue mapping** `attribution.revenue_mapping`                         | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Scheduled reports** `attribution.scheduled_reports`                     | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Data exports** `attribution.data_exports`                               | ●  | ○  | ◐  | ○  | ○  | ◐  |
| **Promote a model from Attribution** `attribution.promote_model` · action | ●  | ○  | ●  | ●  | ○  | ○  |
| **Set Benchmark** `attribution.set_benchmark` · action                    | ●  | ○  | ●  | ●  | ○  | ○  |

### Creative

**Manage Roles** groups **Creative** under **Intelligence**. The module page is `/creatives`, its module-level rights are `LS-CR-01` and `LS-CR-02`, and it carries no action rights.

| Sub-module                                             | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------ | -- | -- | -- | -- | -- | -- |
| **Creative library** `creative.creative_library`       | ●  | ◐  | ●  | ◐  | ○  | ◐  |
| **Performance scoring** `creative.performance_scoring` | ●  | ◐  | ●  | ◐  | ◐  | ◐  |
| **Tag taxonomy** `creative.tag_taxonomy`               | ●  | ○  | ●  | ○  | ○  | ◐  |
| **Brand safety rules** `creative.brand_safety`         | ●  | ○  | ○  | ○  | ○  | ◐  |

### Models

**Manage Roles** groups **Models** under **Causality**. The module page is `/models`, its module-level rights are `LS-MO-01` and `LS-MO-02`, and it carries 3 action rights.

| Sub-module                                              | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Model registry** `models.model_registry`              | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Model runs** `models.model_runs`                      | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Budget allocations** `models.budget_allocations`      | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Scenario library** `models.scenario_library`          | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Diagnostics** `models.diagnostics`                    | ●  | ●  | ◐  | ○  | ○  | ◐  |
| **Export results** `models.export_results`              | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Create / Update** `models.create_update`              | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Merge model** `models.merge_model`                    | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Refresh model** `models.refresh_model`                | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Archive Model** `models.archive_model`                | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Request rollback** `models.request_rollback` · action | ●  | ●  | ○  | ○  | ○  | ○  |
| **Re-train** `models.retrain_model` · action            | ●  | ○  | ●  | ○  | ○  | ○  |
| **Refresh** `models.refresh` · action                   | ●  | ○  | ●  | ○  | ○  | ○  |

### Experiments

**Manage Roles** groups **Experiments** under **Causality**. The module page is `/experiments`, its module-level rights are `LS-EX-01` and `LS-EX-02`, and it carries 1 action right.

| Sub-module                                                       | WA | DP | MS | SP | EX | VW |
| ---------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Experiment builder** `experiments.experiment_builder`          | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Test library** `experiments.test_library`                      | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Results dashboard** `experiments.results_dashboard`            | ●  | ●  | ●  | ◐  | ◐  | ◐  |
| **Holdout groups** `experiments.holdout_groups`                  | ●  | ●  | ●  | ○  | ○  | ◐  |
| **Promote experiment** `experiments.promote_experiment` · action | ●  | ●  | ●  | ○  | ○  | ○  |

Every role grid also carries the key `experiments.create_update_delete_experiment`, which the module registry does not define. No screen reads it as a right, and only its `read` value counts towards whether Experiments opens. It changes nothing today, because Experiments already opens for every role.

### Agents

**Manage Roles** groups **Agents** under **System**. The module page is `/agents`, its module-level rights are `LS-AG-01` and `LS-AG-02`, and it carries no action rights.

| Sub-module                                       | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------ | -- | -- | -- | -- | -- | -- |
| **Agent status** `agents.agent_status`           | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Findings & recommendations** `agents.findings` | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Execution logs** `agents.execution_logs`       | ●  | ◐  | ◐  | ○  | ○  | ◐  |
| **Agent configuration** `agents.agent_config`    | ●  | ○  | ○  | ○  | ○  | ◐  |

### Profiles

**Manage Roles** groups **Profiles** under **System**. The module page is `/profiles`, its module-level rights are `LS-PR-01` and `LS-PR-02`, and it carries no action rights.

| Sub-module                                         | WA | DP | MS | SP | EX | VW |
| -------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Customer profiles** `profiles.customer_profiles` | ●  | ◐  | ◐  | ○  | ○  | ◐  |
| **Profile exports** `profiles.profile_exports`     | ●  | ○  | ○  | ○  | ○  | ◐  |

### Segments

**Manage Roles** groups **Segments** under **System**. The module page is `/segments`, its module-level rights are `LS-SG-01` and `LS-SG-02`, and it carries no action rights.

| Sub-module                                         | WA | DP | MS | SP | EX | VW |
| -------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Audience segments** `segments.audience_segments` | ●  | ●  | ◐  | ◐  | ○  | ◐  |
| **Segment builder** `segments.segment_builder`     | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Segment exports** `segments.segment_exports`     | ●  | ◐  | ○  | ○  | ○  | ◐  |

### Data

**Manage Roles** groups **Data** under **System**. The module page is `/data`, its module-level rights are `LS-DA-01` and `LS-DA-02`, and it carries 4 action rights.

| Sub-module                                                          | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Integrations** `data.integrations`                                | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Transformation rules** `data.transformation`                      | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Taxonomy management** `data.taxonomy`                             | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Pipeline config** `data.pipeline_config`                          | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Schema editor** `data.schema_editor`                              | ●  | ◐  | ○  | ○  | ○  | ◐  |
| **Data quality monitor** `data.dq_monitor`                          | ●  | ●  | ○  | ○  | ○  | ◐  |
| **Connect Integration** `data.connect_integration` · action         | ●  | ●  | ●  | ○  | ○  | ○  |
| **Delete Integration** `data.delete_integration` · action           | ●  | ●  | ○  | ○  | ○  | ○  |
| **Edit / Delete Data Model** `data.edit_delete_data_model` · action | ●  | ●  | ○  | ○  | ○  | ○  |
| **Add Tactic Mapping** `data.add_tactic_mapping` · action           | ●  | ●  | ●  | ○  | ○  | ○  |

Marketing Scientist is ○ on all six non-action Data sub-modules and still opens Data, because `data.connect_integration` and `data.add_tactic_mapping` carry read. Both buttons work for that role.

### Brain

**Manage Roles** groups **Brain** under **System**. The module page is `/brain`, its module-level rights are `LS-BR-01` and `LS-BR-02`, and it carries no action rights.

| Sub-module                                    | WA | DP | MS | SP | EX | VW |
| --------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Knowledge graph** `brain.knowledge_graph`   | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Node exploration** `brain.node_exploration` | ●  | ◐  | ◐  | ○  | ○  | ◐  |

### Config

**Manage Roles** groups **Config** under **System**. The module page is `/config`, its module-level rights are `LS-CF-01` and `LS-CF-02`, and it carries no action rights.

| Sub-module                                              | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Cost configuration** `config.cost_config`             | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Value settings (AOV & CLTV)** `config.value_settings` | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Keyword configuration** `config.keyword_config`       | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Algorithmic weights** `config.algorithmic_weights`    | ●  | ○  | ○  | ○  | ○  | ◐  |

### Artifacts

**Manage Roles** groups **Artifacts** under **Artifacts**. The module page is `/artifacts`, its module-level rights are `LS-AF-01` and `LS-AF-02`, and it carries no action rights.

| Sub-module                                        | WA | DP | MS | SP | EX | VW |
| ------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Artifact library** `artifacts.artifact_library` | ●  | ◐  | ◐  | ●  | ◐  | ◐  |
| **Template builder** `artifacts.template_builder` | ●  | ○  | ◐  | ●  | ○  | ◐  |
| **Publish settings** `artifacts.publish_settings` | ●  | ○  | ○  | ○  | ○  | ◐  |

### Team

**Manage Roles** groups **Team** under **Workspace**. The module page is `/team`, its module-level rights are `LS-TM-01` and `LS-TM-02`, and it carries 4 action rights.

| Sub-module                                            | WA | DP | MS | SP | EX | VW |
| ----------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **View team members** `team.view_members`             | ●  | ◐  | ◐  | ◐  | ◐  | ◐  |
| **Add / deactivate members** `team.manage_members`    | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Edit member permissions** `team.manage_permissions` | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Add Users** `team.add_users` · action               | ●  | ○  | ○  | ○  | ○  | ○  |
| **Edit Permissions** `team.edit_permissions` · action | ●  | ○  | ○  | ○  | ○  | ○  |
| **Create New Role** `team.create_new_role` · action   | ●  | ○  | ○  | ○  | ○  | ○  |
| **Deactivate User** `team.deactivate_user` · action   | ●  | ○  | ○  | ○  | ○  | ○  |

Team opens for every role at **View team members**. The four action rights are what separate a Workspace Admin from everyone else.

### Settings

**Manage Roles** groups **Settings** under **Workspace**. The module page is `/settings`, its module-level rights are `LS-ST-01` and `LS-ST-02`, and it carries 3 action rights.

| Sub-module                                                                  | WA | DP | MS | SP | EX | VW |
| --------------------------------------------------------------------------- | -- | -- | -- | -- | -- | -- |
| **Workspace configuration** `settings.workspace_config`                     | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Notification preferences** `settings.notification_prefs`                  | ●  | ●  | ●  | ●  | ●  | ◐  |
| **API keys & webhooks** `settings.api_access`                               | ●  | ○  | ○  | ○  | ○  | ◐  |
| **Configure Brand Kit** `settings.configure_brand_kit` · action             | ●  | ○  | ○  | ○  | ○  | ○  |
| **Create New Brand Workspace** `settings.create_brand_workspace` · action   | ●  | ○  | ○  | ○  | ○  | ○  |
| **Update Workspace Settings** `settings.update_workspace_settings` · action | ●  | ○  | ○  | ○  | ○  | ○  |

**Notification preferences** is the one Settings sub-module every role can change, which is why Settings reads ● for five of the six roles.

## What each role cannot do

The restriction list for each role, keyed on the role name. A denied module greys in
the sidebar and opens **Access Restricted**. A denied action right leaves its button
on screen at 50% opacity with the tooltip
`Your role ({Role}) cannot {action}. Ask a workspace admin for access.`, where
`{Role}` is the role key (`DataPractitioner`, not `Data Practitioner`) and
`{action}` is the sub-module label in lower case. Denied items inside a row menu are
greyed with no tooltip at all.

### Workspace Admin cannot

- Meet a restriction. No module is closed, and all 23 action rights are held.
- Change what another person's signed-in session opens. A role change is recorded against the member record, and that person's session keeps the role it was issued at sign-in.

### Data Practitioner cannot

- Open **Config**.
- Use 17 of the 23 action rights. It holds `models.request_rollback`, `experiments.promote_experiment`, `data.connect_integration`, `data.delete_integration`, `data.edit_delete_data_model` and `data.add_tactic_mapping`, and nothing else.
- Use `cockpit.publish_artifact`, `plan.promote_to_decision` or `plan.download_export_allocation`.
- Use any Deploy or Attribution action right: `deploy.change_bid_budget`, `deploy.change_status`, `deploy.edit_geo_deploy`, `attribution.promote_model`, `attribution.set_benchmark`.
- Use `models.retrain_model` or `models.refresh`.
- Use any Team action right: `team.add_users`, `team.edit_permissions`, `team.create_new_role`, `team.deactivate_user`.
- Use any Settings action right: `settings.configure_brand_kit`, `settings.create_brand_workspace`, `settings.update_workspace_settings`.

### Marketing Scientist cannot

- Open **Config**.
- Read any non-action part of **Data**. It holds `data.connect_integration` and `data.add_tactic_mapping` and nothing else in Data, and those two grants are what keep the module open.
- Use `data.delete_integration` or `data.edit_delete_data_model`.
- Use `cockpit.publish_artifact`, `plan.promote_to_decision` or `models.request_rollback`.
- Use any Team action right: `team.add_users`, `team.edit_permissions`, `team.create_new_role`, `team.deactivate_user`.
- Use any Settings action right: `settings.configure_brand_kit`, `settings.create_brand_workspace`, `settings.update_workspace_settings`.

### Strategic Planner cannot

- Open **Profiles**, **Data** or **Config**.
- Use any Models or Experiments action right: `models.request_rollback`, `models.retrain_model`, `models.refresh`, `experiments.promote_experiment`.
- Use any Data action right: `data.connect_integration`, `data.delete_integration`, `data.edit_delete_data_model`, `data.add_tactic_mapping`.
- Use any Team action right: `team.add_users`, `team.edit_permissions`, `team.create_new_role`, `team.deactivate_user`.
- Use any Settings action right: `settings.configure_brand_kit`, `settings.create_brand_workspace`, `settings.update_workspace_settings`.

### Executive cannot

- Open **Profiles**, **Segments**, **Data** or **Config**.
- Hold more than three action rights. `cockpit.publish_artifact`, `plan.promote_to_decision` and `plan.download_export_allocation` are the whole set, and the other 20 are denied.
- Use any Deploy or Attribution action right: `deploy.change_bid_budget`, `deploy.change_status`, `deploy.edit_geo_deploy`, `attribution.promote_model`, `attribution.set_benchmark`.
- Use any Models or Experiments action right: `models.request_rollback`, `models.retrain_model`, `models.refresh`, `experiments.promote_experiment`.
- Use any Data, Team or Settings action right.
- Hold Manage access on anything except **Settings**, where the one manage grant is `settings.notification_prefs`.

### Viewer cannot

- Use any action right anywhere. All 23 are denied, which makes Viewer the only role that triggers nothing.
- Hold Manage access on any sub-module of any module. Of its 89 cells, 66 read ◐ and the 23 action rights read ○.
- Be selected in **Invite User**, or appear in the **Preset Roles** list in **Manage Roles**. Put someone on Viewer with **Change role** on their **Manage Team** row.

No module is closed to a Viewer. All 16 read ◐, including **Data**, **Config** and
**Team**.

None of these lists is a dead end. Select **Request Access** on the **Access
Restricted** page, or ask a Workspace Admin to move the person onto another role —
see [Ask for access, and review requests](doc:access-requests).

## Custom roles

Nothing on this page describes a custom role. A custom role is edited as the same 55
rights, and the rights it carries are held in browser storage rather than in the
source grid. Two things create one.

| How it is created                            | Where                                    | The name                              |
| -------------------------------------------- | ---------------------------------------- | ------------------------------------- |
| A Workspace Admin builds it                  | **Team > Manage Roles** > **New role**   | Whatever is typed in the name field   |
| A Workspace Admin approves an access request | **Team > Access Requests** > **Approve** | Generated as `{Base role} + {Module}` |

The generated name takes the label of the role the requester already holds, then
each granted module label in registry order, joined by `+`. Executive plus a
granted Data module becomes `Executive + Data`, and a second approval for the same
person extends the same name, as in `Executive + Data + Config`. A requester who is
already a Workspace Admin gets no generated role, because there is nothing to add.
The modules a generated role restates for its base role come from a separate legacy
per-role URL list (`ROLE_PERMISSIONS` in `frontend/lib/navigation.ts`), not from the
grid on this page, so the two can differ.

For validation, treat any role name outside the six keys in the table above as
holding no right on this page: the action-right gate resolves a custom role by exact
name from a browser store that no mounted screen writes, so every action right is
denied for it. Building one is on [Create a custom role](doc:custom-roles).

<Callout icon="🚧" theme="warn">
  ### Role definitions are not shared, and assigning one moves nobody

  A role definition is written to one browser tab's session storage and never leaves it, so no colleague and no other device sees the role. Assigning any role — preset, custom or generated — does not change what the assigned person can open, because a session's role is fixed at sign-in. See [What's live in this build](doc:whats-live-in-this-build).
</Callout>

## Machine-readable matrix

One block, the same grid, for programmatic use. `roles[key].modules` gives the
module-level result (`manage`, `read` or `none`), `roles[key].action_rights` gives
every action key the role holds, and `modules[id].action_rights` gives every action
key that exists. An agent card's `requires_rights` entry is valid when it appears in
some `modules[id].action_rights`, and that card's `requires_role` list must equal
the set of roles whose `action_rights` contains the key.

```json permissions
{
  "generated_from": {
    "sources": ["frontend/lib/role-defaults.ts#ROLE_SUB_MODULE_DEFAULTS", "frontend/lib/module-registry.ts#MODULE_REGISTRY", "frontend/lib/access-rights.ts#buildAccessRightsRegistry"],
    "notation": {"manage": "F - read and fullAccess", "read": "R - read, no fullAccess", "none": "N - neither"},
    "module_open_rule": "A module opens when at least one of its sub-modules carries read. Action sub-modules count, because a granted action carries read as well.",
    "action_rule": "An action right is allowed only when its module opens and the action key itself carries fullAccess. An unlisted key is denied, and read on an action key is an explicit deny.",
    "always_open": ["/help-center"],
    "counts": {"modules": 16, "sub_modules": 89, "rights": 55, "read_rights": 16, "manage_rights": 16, "action_rights": 23, "modules_with_action_rights": 9},
    "unregistered_keys": ["experiments.create_update_delete_experiment"],
    "role_key_aliases": {"admin": "WorkspaceAdmin", "analyst": "DataPractitioner", "executive": "Executive", "viewer": "Viewer"},
    "generated_on": "2026-09-13",
    "hand_edited": false
  },
  "app_build": "ls4x@feature/LS4X-155-support-help-center",
  "roles": {
    "WorkspaceAdmin": {
      "label": "Workspace Admin",
      "tagline": "Full platform access",
      "listed_in_manage_roles": true,
      "offered_in_invite_user": true,
      "rights_held": 55,
      "rights_total": 55,
      "closed_modules": [],
      "modules": {"cockpit": "manage", "plan": "manage", "deploy": "manage", "attribution": "manage", "creative": "manage", "models": "manage", "experiments": "manage", "agents": "manage", "profiles": "manage", "segments": "manage", "data": "manage", "brain": "manage", "config": "manage", "artifacts": "manage", "team": "manage", "settings": "manage"},
      "action_rights": [
        "cockpit.publish_artifact",
        "plan.promote_to_decision",
        "plan.download_export_allocation",
        "deploy.change_bid_budget",
        "deploy.change_status",
        "deploy.edit_geo_deploy",
        "attribution.promote_model",
        "attribution.set_benchmark",
        "models.request_rollback",
        "models.retrain_model",
        "models.refresh",
        "experiments.promote_experiment",
        "data.connect_integration",
        "data.delete_integration",
        "data.edit_delete_data_model",
        "data.add_tactic_mapping",
        "team.add_users",
        "team.edit_permissions",
        "team.create_new_role",
        "team.deactivate_user",
        "settings.configure_brand_kit",
        "settings.create_brand_workspace",
        "settings.update_workspace_settings"
      ]
    },
    "DataPractitioner": {
      "label": "Data Practitioner",
      "tagline": "Data pipelines & measurement infrastructure",
      "listed_in_manage_roles": true,
      "offered_in_invite_user": true,
      "rights_held": 27,
      "rights_total": 55,
      "closed_modules": ["config"],
      "modules": {"cockpit": "read", "plan": "read", "deploy": "read", "attribution": "manage", "creative": "read", "models": "manage", "experiments": "manage", "agents": "read", "profiles": "read", "segments": "manage", "data": "manage", "brain": "read", "config": "none", "artifacts": "read", "team": "read", "settings": "manage"},
      "action_rights": ["models.request_rollback", "experiments.promote_experiment", "data.connect_integration", "data.delete_integration", "data.edit_delete_data_model", "data.add_tactic_mapping"]
    },
    "MarketingScientist": {
      "label": "Marketing Scientist",
      "tagline": "Attribution, experiments & creative intelligence",
      "listed_in_manage_roles": true,
      "offered_in_invite_user": true,
      "rights_held": 29,
      "rights_total": 55,
      "closed_modules": ["config"],
      "modules": {"cockpit": "read", "plan": "read", "deploy": "read", "attribution": "manage", "creative": "manage", "models": "read", "experiments": "manage", "agents": "read", "profiles": "read", "segments": "read", "data": "read", "brain": "read", "config": "none", "artifacts": "read", "team": "read", "settings": "manage"},
      "action_rights": [
        "plan.download_export_allocation",
        "deploy.change_bid_budget",
        "deploy.change_status",
        "deploy.edit_geo_deploy",
        "attribution.promote_model",
        "attribution.set_benchmark",
        "models.retrain_model",
        "models.refresh",
        "experiments.promote_experiment",
        "data.connect_integration",
        "data.add_tactic_mapping"
      ]
    },
    "StrategicPlanner": {
      "label": "Strategic Planner",
      "tagline": "Campaign planning & budget deployment",
      "listed_in_manage_roles": true,
      "offered_in_invite_user": true,
      "rights_held": 24,
      "rights_total": 55,
      "closed_modules": ["profiles", "data", "config"],
      "modules": {"cockpit": "read", "plan": "manage", "deploy": "read", "attribution": "read", "creative": "read", "models": "read", "experiments": "read", "agents": "read", "profiles": "none", "segments": "read", "data": "none", "brain": "read", "config": "none", "artifacts": "manage", "team": "read", "settings": "manage"},
      "action_rights": ["cockpit.publish_artifact", "plan.promote_to_decision", "plan.download_export_allocation", "deploy.change_bid_budget", "deploy.change_status", "deploy.edit_geo_deploy", "attribution.promote_model", "attribution.set_benchmark"]
    },
    "Executive": {
      "label": "Executive",
      "tagline": "Read-only strategic overview",
      "listed_in_manage_roles": true,
      "offered_in_invite_user": true,
      "rights_held": 16,
      "rights_total": 55,
      "closed_modules": ["profiles", "segments", "data", "config"],
      "modules": {"cockpit": "read", "plan": "read", "deploy": "read", "attribution": "read", "creative": "read", "models": "read", "experiments": "read", "agents": "read", "profiles": "none", "segments": "none", "data": "none", "brain": "read", "config": "none", "artifacts": "read", "team": "read", "settings": "manage"},
      "action_rights": ["cockpit.publish_artifact", "plan.promote_to_decision", "plan.download_export_allocation"]
    },
    "Viewer": {
      "label": "Viewer",
      "tagline": "Read-only across every module",
      "listed_in_manage_roles": false,
      "offered_in_invite_user": false,
      "rights_held": 16,
      "rights_total": 55,
      "closed_modules": [],
      "modules": {"cockpit": "read", "plan": "read", "deploy": "read", "attribution": "read", "creative": "read", "models": "read", "experiments": "read", "agents": "read", "profiles": "read", "segments": "read", "data": "read", "brain": "read", "config": "read", "artifacts": "read", "team": "read", "settings": "read"},
      "action_rights": []
    }
  },
  "modules": {
    "cockpit": {
      "label": "Cockpit",
      "code": "CK",
      "route": "/cockpit",
      "section": "Platform",
      "read_right": "LS-CK-01",
      "manage_right": "LS-CK-02",
      "sub_modules": {"overview_dashboard": "Overview & KPIs", "recommendations": "Recommendations", "alerts_config": "Alert configuration"},
      "action_rights": {"cockpit.publish_artifact": "Publish Artifact from Cockpit"}
    },
    "plan": {
      "label": "Plan",
      "code": "PL",
      "route": "/planning",
      "section": "Action",
      "read_right": "LS-PL-01",
      "manage_right": "LS-PL-02",
      "sub_modules": {"scenario_workspace": "Scenario workspace", "budget_simulation": "Budget simulation", "export_plans": "Export plans", "run_simulation": "Run Simulation"},
      "action_rights": {"plan.promote_to_decision": "Promote to Decision", "plan.download_export_allocation": "Download / Export Allocation"}
    },
    "deploy": {
      "label": "Deploy",
      "code": "DP",
      "route": "/decisions",
      "section": "Action",
      "read_right": "LS-DP-01",
      "manage_right": "LS-DP-02",
      "sub_modules": {"decision_queue": "Decision queue", "review_approve": "Review & approve", "activity_log": "Activity log", "change_bid": "Change bid", "budget": "Budget"},
      "action_rights": {"deploy.change_bid_budget": "Change Bid/Budget", "deploy.change_status": "Change Status", "deploy.edit_geo_deploy": "Edit Geo Deploy"}
    },
    "attribution": {
      "label": "Attribution",
      "code": "AT",
      "route": "/attribution",
      "section": "Intelligence",
      "read_right": "LS-AT-01",
      "manage_right": "LS-AT-02",
      "sub_modules": {"channel_overview": "Channel overview", "attribution_rules": "Attribution rules", "conversion_events": "Conversion events", "revenue_mapping": "Revenue mapping", "scheduled_reports": "Scheduled reports", "data_exports": "Data exports"},
      "action_rights": {"attribution.promote_model": "Promote a model from Attribution", "attribution.set_benchmark": "Set Benchmark"}
    },
    "creative": {
      "label": "Creative",
      "code": "CR",
      "route": "/creatives",
      "section": "Intelligence",
      "read_right": "LS-CR-01",
      "manage_right": "LS-CR-02",
      "sub_modules": {"creative_library": "Creative library", "performance_scoring": "Performance scoring", "tag_taxonomy": "Tag taxonomy", "brand_safety": "Brand safety rules"},
      "action_rights": {}
    },
    "models": {
      "label": "Models",
      "code": "MO",
      "route": "/models",
      "section": "Causality",
      "read_right": "LS-MO-01",
      "manage_right": "LS-MO-02",
      "sub_modules": {"model_registry": "Model registry", "model_runs": "Model runs", "budget_allocations": "Budget allocations", "scenario_library": "Scenario library", "diagnostics": "Diagnostics", "export_results": "Export results", "create_update": "Create / Update", "merge_model": "Merge model", "refresh_model": "Refresh model", "archive_model": "Archive Model"},
      "action_rights": {"models.request_rollback": "Request rollback", "models.retrain_model": "Re-train", "models.refresh": "Refresh"}
    },
    "experiments": {
      "label": "Experiments",
      "code": "EX",
      "route": "/experiments",
      "section": "Causality",
      "read_right": "LS-EX-01",
      "manage_right": "LS-EX-02",
      "sub_modules": {"experiment_builder": "Experiment builder", "test_library": "Test library", "results_dashboard": "Results dashboard", "holdout_groups": "Holdout groups"},
      "action_rights": {"experiments.promote_experiment": "Promote experiment"}
    },
    "agents": {
      "label": "Agents",
      "code": "AG",
      "route": "/agents",
      "section": "System",
      "read_right": "LS-AG-01",
      "manage_right": "LS-AG-02",
      "sub_modules": {"agent_status": "Agent status", "findings": "Findings & recommendations", "execution_logs": "Execution logs", "agent_config": "Agent configuration"},
      "action_rights": {}
    },
    "profiles": {
      "label": "Profiles",
      "code": "PR",
      "route": "/profiles",
      "section": "System",
      "read_right": "LS-PR-01",
      "manage_right": "LS-PR-02",
      "sub_modules": {"customer_profiles": "Customer profiles", "profile_exports": "Profile exports"},
      "action_rights": {}
    },
    "segments": {
      "label": "Segments",
      "code": "SG",
      "route": "/segments",
      "section": "System",
      "read_right": "LS-SG-01",
      "manage_right": "LS-SG-02",
      "sub_modules": {"audience_segments": "Audience segments", "segment_builder": "Segment builder", "segment_exports": "Segment exports"},
      "action_rights": {}
    },
    "data": {
      "label": "Data",
      "code": "DA",
      "route": "/data",
      "section": "System",
      "read_right": "LS-DA-01",
      "manage_right": "LS-DA-02",
      "sub_modules": {"integrations": "Integrations", "transformation": "Transformation rules", "taxonomy": "Taxonomy management", "pipeline_config": "Pipeline config", "schema_editor": "Schema editor", "dq_monitor": "Data quality monitor"},
      "action_rights": {"data.connect_integration": "Connect Integration", "data.delete_integration": "Delete Integration", "data.edit_delete_data_model": "Edit / Delete Data Model", "data.add_tactic_mapping": "Add Tactic Mapping"}
    },
    "brain": {
      "label": "Brain",
      "code": "BR",
      "route": "/brain",
      "section": "System",
      "read_right": "LS-BR-01",
      "manage_right": "LS-BR-02",
      "sub_modules": {"knowledge_graph": "Knowledge graph", "node_exploration": "Node exploration"},
      "action_rights": {}
    },
    "config": {
      "label": "Config",
      "code": "CF",
      "route": "/config",
      "section": "System",
      "read_right": "LS-CF-01",
      "manage_right": "LS-CF-02",
      "sub_modules": {"cost_config": "Cost configuration", "value_settings": "Value settings (AOV & CLTV)", "keyword_config": "Keyword configuration", "algorithmic_weights": "Algorithmic weights"},
      "action_rights": {}
    },
    "artifacts": {
      "label": "Artifacts",
      "code": "AF",
      "route": "/artifacts",
      "section": "Artifacts",
      "read_right": "LS-AF-01",
      "manage_right": "LS-AF-02",
      "sub_modules": {"artifact_library": "Artifact library", "template_builder": "Template builder", "publish_settings": "Publish settings"},
      "action_rights": {}
    },
    "team": {
      "label": "Team",
      "code": "TM",
      "route": "/team",
      "section": "Workspace",
      "read_right": "LS-TM-01",
      "manage_right": "LS-TM-02",
      "sub_modules": {"view_members": "View team members", "manage_members": "Add / deactivate members", "manage_permissions": "Edit member permissions"},
      "action_rights": {"team.add_users": "Add Users", "team.edit_permissions": "Edit Permissions", "team.create_new_role": "Create New Role", "team.deactivate_user": "Deactivate User"}
    },
    "settings": {
      "label": "Settings",
      "code": "ST",
      "route": "/settings",
      "section": "Workspace",
      "read_right": "LS-ST-01",
      "manage_right": "LS-ST-02",
      "sub_modules": {"workspace_config": "Workspace configuration", "notification_prefs": "Notification preferences", "api_access": "API keys & webhooks"},
      "action_rights": {"settings.configure_brand_kit": "Configure Brand Kit", "settings.create_brand_workspace": "Create New Brand Workspace", "settings.update_workspace_settings": "Update Workspace Settings"}
    }
  }
}
```

The key `experiments.create_update_delete_experiment`, listed under
`generated_from.unregistered_keys`, exists in every role grid and in no module, so
no screen reads it as a right — only its `read` value counts, and only towards
whether Experiments opens. Treat it as absent when validating a `requires_rights`
list.

## Related

<Cards columns="2">
  <Card title="Roles: what each one opens" href="doc:roles-and-permissions" icon="fa-user-shield">
    The model behind this grid, and the six role cards.
  </Card>

  <Card title="Create a custom role" href="doc:custom-roles" icon="fa-user-pen">
    The Read, Manage and Actions grid a Workspace Admin edits.
  </Card>
</Cards>

---
title: '[4.0][ReadyForQA] Invite, Change, and deactivate Teammates'
excerpt: >-
  Invite people to your workspace from Team > Manage Team, change the role a
  member holds, and deactivate, re-invite or revoke access.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Columns layout="fixed">
  <Column>
    Invite someone into your workspace, change a member's role, or remove their access. Everything here happens on **Team > Manage Team**, reached from the user menu at the bottom of the sidebar.
  </Column>
</Columns>

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin. Other roles can open the page and read both lists but see the buttons dimmed with the tooltip `Your role (<Role>) cannot add users. Ask a workspace admin for access.`

  **Where:** Sidebar user menu > **Team** > **Manage Team**

  **Time:** About 2 minutes per person.
</Callout>

## Before you start

- You are signed in as a Workspace Admin.
- **Team > Manage Team** is open.
- You know which role the person needs.

## Invite a teammate

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin (`team.add_users`)
</Callout>

1. In the sidebar, open the user menu and select **Team**.
2. **Manage Team** opens by default; select the tab if you are on another one.
3. Select **Invite User**, CTA button present on top-right corner of the page.
4. In **Name**, enter the person's full name.
5. In **Email**, enter their work email address.
6. In **Role**, select a role. The default is **Marketing Scientist**.
7. In **Persona**, select a persona. The default is **Generalist**.
8. Optional: in **Personal message (optional)**, enter up to 500 characters.
9. Select **Invite User**.

The button reads **Inviting...** while it works. If the dialog stays open, a field failed validation — fix the field named in red and return to step 9.

You're done when:

- The toast `User invited` has appeared.
- The **Inactive** toggle shows a **Pending** row carrying the email address you entered.
- That row's **Invited** date is today.

The **Role** list offers Workspace Admin, Data Practitioner, Marketing Scientist, Strategic Planner and Executive, then any custom role in this browser session, then **+ Create Custom Role**. Selecting **+ Create Custom Role** shows the link **Configure custom role permissions**, which opens **Manage Roles**. Submitting while it is selected shows the error toast<br />`Please create a custom role in Manage Roles before inviting the user`, so build
the role first on [Create a custom role](doc:custom-roles).

## Change someone's role

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin (`team.edit_permissions`)
</Callout>

1. On **Team > Manage Team**, select **Open menu** on the member's row.
2. Select **Change role**.
3. Select the new role. The list marks the role they hold now `(current)`.
4. Select **Apply**.

You should see the toast `<Name>'s role updated to <roleValue>` and the new role on that member's row. **Apply** stays disabled until you pick a role different from the current one.

Changing a role here does not change what that person can open: a signed-in session keeps the role it was given at sign-in.

## Deactivate a member

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin (`team.deactivate_user`)
</Callout>

1. On **Team > Manage Team**, select **Open menu** on the member's row.
2. Select **Deactivate**.
3. Read the dialog: `Are you sure you want to deactivate <Name>? They will immediately lose access to the workspace.`
4. Select **Deactivate**.

You should see the toast `User status updated` and the row leaves the **Active&#x20;**&#x6C;ist. The person does not reappear under **Inactive > Deactivated**.

<Callout icon="❗️" theme="error">
  ### There is no undo

  Deactivating removes the member from the list, and this page has no reactivate control. To bring the person back, invite them again as a new member; they start at **Pending**.
</Callout>

## Re-invite an expired invitee

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin (`team.add_users`)
</Callout>

1. On **Team > Manage Team**, select **Inactive**.
2. Under **Expired**, select **Open menu** on the row.
3. Select **Re-invite**.
4. If **Role** or **Persona** is blank, select a value in each.
5. Select **Send Invite**.

The button reads **Sending...** while it works. You should see the toast `User re-invited` and a new row under **Inactive > Pending**. The **Expired** row stays: re-inviting adds a row rather than replacing one, so the same person is listed twice.

## Revoke a pending invitation

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin (`team.deactivate_user`)
</Callout>

1. On **Team > Manage Team**, select **Inactive**.
2. Under **Pending**, select **Open menu** on the row.
3. Select **Revoke invitation**.
4. Select **Revoke**.

You should see the toast `Invitation to <Name> revoked` and the row disappears from **Pending**. The dialog warns the invite link will stop working; none is generated in this build, so only the row goes.

## Reference

The **Team Members** toggle and section labels show each person's state.

| Status      | Where it shows                                          | What it means                                       | Who acts next                                      |
| ----------- | ------------------------------------------------------- | --------------------------------------------------- | -------------------------------------------------- |
| Active      | **Active** toggle                                       | Holds a role in this workspace                      | Workspace Admin: **Change role** or **Deactivate** |
| Pending     | **Inactive > Pending**, date column **Invited**         | Invited, not yet joined                             | Workspace Admin: **Revoke invitation**             |
| Expired     | **Inactive > Expired**, date column **Expired**         | Seeded state only; nothing moves an invitation here | Workspace Admin: **Re-invite**                     |
| Deactivated | **Inactive > Deactivated**, date column **Last active** | Non-active, neither invited nor expired             | Nobody; this section effectively never appears     |

The full grid of role by module by right is on [Permissions matrix](doc:permissions-matrix-reference).

## FAQ

### Why can't I pick Viewer when I invite someone?

Viewer is not in the **Invite User** role list. Invite the person on another role,
then use **Change role** on their row, which does list Viewer alongside the other
five preset roles.

### Should I change someone's role or approve their access request?

Change the role when the person's job changed and they need a different shape of
access. Approve an access request when they need one more module on top of what
they have. Neither changes what their signed-in session can open in this build.
See [Access requests](doc:access-requests).

### Does the person get an email?

No email is sent. No invitation email, invite link or token is generated in this
build, so send the person the workspace URL yourself. The invitation also
disappears on a full page reload.

### Why does the role toast print a name without spaces?

The toast and the denied-state tooltip print the internal role value, so Strategic
Planner reads `StrategicPlanner` and Data Practitioner reads `DataPractitioner`.
The row tag, the **Change role** list and the invite dialog print the spaced
label. Both name one role.

### I clicked a member's Role tag and got "No permission data available" — what is that?

The coloured Role tag on a member's row is clickable and opens a role-permissions
popover, but for this build's seeded roles it reads `No permission data available.`
— a mock surface, not a sign your permission data is missing. To see what a role
can do, open the **Manage Roles** tab or the
[Permissions matrix](doc:permissions-matrix-reference).

### Someone is missing from the list — where did they go?

Three things remove a row: each section shows at most 10 rows and hides the rest;
deactivating deletes the row; and a full page reload restores the seeded list,
dropping everyone you added. The **Active** list also hides the row whose email
matches the signed-in user's, but those addresses never match the seeded members
here, so it hides nobody.

## Related

<Cards columns="2">
  <Card title="Roles and permissions" href="doc:roles-and-permissions" icon="fa-user-shield">
    What each role opens, and what it can do.
  </Card>

  <Card title="Create a custom role" href="doc:custom-roles" icon="fa-sliders">
    Build a role the preset six do not cover.
  </Card>

  <Card title="Access requests" href="doc:access-requests" icon="fa-key">
    The other way people get a module.
  </Card>
</Cards>

## Agent card

```yaml agent
task: team-manage-members
title: Invite, change, and deactivate teammates
type: howto
surface: Team
page: https://docs.lifesight.io/docs/manage-your-team
last_verified: 2026-09-13
app_build: "ls4x@feature/LS4X-155"

state: preview
persistence: page
state_note: >
  The member list and every change to it live in this browser's memory. A full
  page reload restores the seeded list. No invitation email, invite link or token
  is ever generated. The personal message is accepted and never displayed again.
  Changing a member's role does not change what that person can open, because a
  signed-in session carries the role it was given at sign-in.

requires_role: [Workspace Admin]
requires_rights: [team.add_users, team.edit_permissions, team.deactivate_user, team.create_new_role]
denied_ux: >
  Buttons stay visible at 50% opacity with the tooltip
  "Your role (<Role>) cannot <action>. Ask a workspace admin for access."
  where <action> is "add users", "edit permissions", "deactivate user" or
  "create new role", and <Role> is the internal role value, e.g.
  "MarketingScientist". Row-menu items — Change role, Deactivate, Revoke
  invitation — are greyed out instead and carry no tooltip. The page itself and
  both lists stay readable for every role.

entry_point: "Sidebar user menu > Team > Manage Team"
url: "/team?tab=team"
preconditions:
  - Signed in as a Workspace Admin.
  - The Team page is open on the Manage Team tab.

ui_strings:
  tab: "Manage Team"
  card: "Team Members"
  toggle: ["Active", "Inactive"]
  sections: ["Pending", "Expired", "Deactivated"]
  primary_action: "Invite User"
  dialog_title: "Invite User"
  fields: ["Name", "Email", "Role", "Persona", "Personal message (optional)"]
  submit: "Invite User"
  busy: "Inviting..."
  row_menu: "Open menu"
  change_role: "Change role"
  change_role_submit: "Apply"
  deactivate: "Deactivate"
  revoke: "Revoke invitation"
  revoke_submit: "Revoke"
  reinvite: "Re-invite"
  reinvite_submit: "Send Invite"
  reinvite_busy: "Sending..."
  custom_role_option: "+ Create Custom Role"
  custom_role_link: "Configure custom role permissions"

procedures:
  - id: invite-a-teammate
    goal: Add a person to the workspace with a role and a persona.
    steps:
      - 'In the sidebar, open the user menu and select "Team".'
      - '"Manage Team" opens by default; select the tab if you are on another one.'
      - 'Select "Invite User".'
      - 'In "Name", enter the person''s full name.'
      - 'In "Email", enter their work email address.'
      - 'In "Role", select a role. The default is "Marketing Scientist".'
      - 'In "Persona", select a persona. The default is "Generalist".'
      - 'Optional: in "Personal message (optional)", enter up to 500 characters.'
      - 'Select "Invite User".'
    expect: 'Toast "User invited" with description "<Name> (<Role>) has been invited."'
    verify: 'Team > Inactive > Pending contains a row whose Email cell equals the address entered.'
    on_fail: 'The dialog stays open when validation fails. Fix the field named in red and return to step 9.'
    reversible: true
    undo: 'On the Pending row, select "Open menu", then "Revoke invitation", then "Revoke".'
  - id: change-someones-role
    goal: Move an active member onto a different role.
    steps:
      - 'On "Team > Manage Team", select "Open menu" on the member''s row.'
      - 'Select "Change role".'
      - 'Select the new role. The list marks the role they hold now "(current)".'
      - 'Select "Apply".'
    expect: 'Toast "<Name>''s role updated to <roleValue>" — prints the internal value, e.g. "StrategicPlanner".'
    verify: 'The Role tag on that member''s row shows the new role.'
    on_fail: '"Apply" stays disabled until a role different from the current one is selected.'
    reversible: true
    undo: 'Repeat with the previous role.'
  - id: deactivate-a-member
    goal: Remove an active member's access.
    steps:
      - 'On "Team > Manage Team", select "Open menu" on the member''s row.'
      - 'Select "Deactivate".'
      - 'Read the dialog: "Are you sure you want to deactivate <Name>? They will immediately lose access to the workspace."'
      - 'Select "Deactivate".'
    expect: 'Toast "User status updated". The row leaves the Active list.'
    verify: 'The Active list no longer contains the row, and Inactive > Deactivated does not gain one.'
    reversible: false
    undo: 'None in-product. Invite the person again as a new member.'
  - id: re-invite-an-expired-invitee
    goal: Send a fresh invitation to a person sitting in the Expired section.
    steps:
      - 'On "Team > Manage Team", select "Inactive".'
      - 'Under "Expired", select "Open menu" on the row.'
      - 'Select "Re-invite".'
      - 'If "Role" or "Persona" is blank, select a value in each.'
      - 'Select "Send Invite".'
    expect: 'Toast "User re-invited" with description "<Name> has been re-invited."'
    verify: 'Inactive > Pending gains a row for that email address. The Expired row is still there.'
    reversible: true
    undo: 'On the new Pending row, select "Open menu", then "Revoke invitation", then "Revoke".'
  - id: revoke-a-pending-invitation
    goal: Withdraw an invitation that has not been accepted.
    steps:
      - 'On "Team > Manage Team", select "Inactive".'
      - 'Under "Pending", select "Open menu" on the row.'
      - 'Select "Revoke invitation".'
      - 'Select "Revoke".'
    expect: 'Toast "Invitation to <Name> revoked".'
    verify: 'Inactive > Pending no longer contains the row.'
    reversible: false
    undo: 'None in-product. Invite the person again.'

limits:
  - Each section shows at most 10 rows; pagination, search, sort and filters are absent.
  - '"Personal message (optional)" is cut at 500 characters and is never displayed again.'
  - The Active list is coded to hide the row whose email matches the signed-in user's, but the sign-in addresses in this build never match the seeded member addresses, so no row is hidden in practice.
  - Re-invite adds a second row and leaves the Expired row in place.
  - Deactivate deletes the row; Inactive > Deactivated effectively never appears.
  - No email address is checked for duplicates, so one address can hold several rows.

errors:
  - when: Name is shorter than 2 characters
    message: "Name must be at least 2 characters"
    fix: Enter a name of 2 characters or more.
  - when: Email is not a valid address
    message: "Invalid email address"
    fix: Enter a complete work email address.
  - when: '"+ Create Custom Role" is selected on submit. Shown as an error toast, not as a field message.'
    message: "Please create a custom role in Manage Roles before inviting the user"
    fix: 'Create the role on Team > Manage Roles first, then reopen the dialog.'

agent_rules:
  - Do not tell the user an invitation email or invite link was sent. Neither exists in this build.
  - Do not report any change on this page as saved. It is lost on a full page reload.
  - Do not tell the user a role change grants or removes access. The session role is fixed at sign-in.
  - Do not offer a reactivate step after deactivating. The page has none.
  - Do not claim a member is absent from the workspace on the evidence of the list alone; each section shows at most 10 rows.

related: [roles-and-permissions, custom-roles, access-requests, permissions-matrix-reference, whats-live-in-this-build]
```

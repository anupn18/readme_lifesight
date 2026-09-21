---
title: '[4.0][Updated] Invite, Change, and deactivate Teammates'
excerpt: >-
  Invite people to your workspace from Team > Manage Team, change the role a
  member holds, and deactivate, re-invite or revoke access.
deprecated: false
hidden: true
metadata:
  title: Invite, Change, and deactivate Teammates in Lifesight
  keywords:
    - Lifesight Team invites
  robots: index
---
<Columns layout="fixed">
  <Column>
    Your team lives in **Team > Manage Team**. Everything to do with who is in your workspace happens there: bringing someone in, moving them to a different role as their job changes, and removing access when they leave.

    Getting roles right on the way in saves work later. Decide what shape of access a person needs before you invite them, because the role you pick at invite decides what they can open from day one.
  </Column>
</Columns>

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin. Other roles can open the page and read both lists but see the buttons dimmed with the tooltip `Your role (<Role>) cannot add users. Ask a workspace admin for access.`

  **Where:** Sidebar user menu > **Team** > **Manage Team**
</Callout>

## Before you start

- You are signed in as &#x61;**&#x20;Workspace Admin.**
- **Team > Manage Team** is open.
- You know which role the person needs. For what each role opens, see Roles and permissions.
- If the person needs a custom role, build it first on Create a custom role. You cannot create one from the invite dialog.

## Invite a teammate

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin&#x20;
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

![](https://files.readme.io/fbf95f71b208ccdd09438b0ba676603ffdfa4eb7fbcc1671f1e1871133ee0cc7-Screenshot_2026-09-21_at_7.49.54_AM.png)

The button reads **Inviting...** while it works. If the dialog stays open, a field failed validation, fix the field named in red and return to step 9.

You're done when:

- The toast `User invited` has appeared.
- The **Inactive** toggle shows a **Pending** row carrying the email address you entered.
- That row's **Invited** date is today.

**About the role list:&#x20;**&#x49;t offers Workspace Admin, Data Practitioner, Marketing Scientist, Strategic Planner, and Executive, then any custom role created in this browser session, then +**&#x20;Create Custom Role.** Selecting + Create Custom Role shows the link **Configure custom role permissions**, which opens Manage Roles.&#x20;

Submitting while it is selected shows the error toast `Please create a custom role in Manage Roles before inviting the user`, so buildthe role first on [Create a custom role](doc:custom-roles).

No invitation email, link, or token is generated in this build. Share the workspace URL with the person directly so they know where to sign in.

## Change someone's role

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin&#x20;
</Callout>

1. On **Team > Manage Team**, select **Open menu** on the member's row.
2. Select **Change role**.
3. Select the new role. The list marks the role they hold now `(current)`.
4. Select **Apply**.

![](https://files.readme.io/e267282d09ecf41e9d939182ac7338b8218187d8515dac9c4dd9dacfe2b772d7-Screenshot_2026-09-21_at_7.50.51_AM.png)

You should see the toast `<Name>'s role updated to <roleValue>` and the new role on that member's row. **Apply** stays disabled until you pick a role different from the current one.

Changing a role here does not change what that person can open: a signed-in session keeps the role it was given at sign-in.

## Deactivate a member

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin
</Callout>

1. On **Team > Manage Team**, select **Open menu** on the member's row.
2. Select **Deactivate**.
3. Read the dialog: `Are you sure you want to deactivate <Name>? They will immediately lose access to the workspace.`
4. Select **Deactivate**.

![](https://files.readme.io/df48ceaa832c5726513b55f46345a4efbf5891518db40cdb4c00ba9b220084cc-Screenshot_2026-09-21_at_7.51.14_AM.png)

You should see the toast `User status updated` and the row leaves the **Active&#x20;**&#x6C;ist. The person does not reappear under **Inactive > Deactivated**.

<Callout icon="❗️" theme="error">
  ### There is no undo

  Deactivating removes the member from the list, and this page has no reactivate control. To bring the person back, invite them again as a new member; they start at **Pending**.
</Callout>

## Re-invite an expired invitee

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin&#x20;
</Callout>

1. On **Team > Manage Team**, select **Inactive**.
2. Under **Expired**, select **Open menu** on the row.
3. Select **Re-invite**.
4. If **Role** or **Persona** is blank, select a value in each.
5. Select **Send Invite**.

![](https://files.readme.io/e8e89d3caf55a20da5b7291c890fed781e54676a01a7d87c7eed77d57be16f57-Screenshot_2026-09-21_at_7.51.46_AM.png)

The button reads **Sending...** while it works. You should see the toast `User re-invited` and a new row under **Inactive > Pending**. The **Expired** row stays: re-inviting adds a row rather than replacing one, so the same person is listed twice.

## Revoke a pending invitation

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Workspace Admin&#x20;
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

Viewer is not in the Invite User role list. Invite the person on another role, then use Change role on their row, which lists Viewer alongside the other five preset roles.

### Should I change someone's role or approve their access request?

Change the role when the person's job changed and they need a different shape of access. Approve an access request when they need one more module on top of what they have. Neither changes what their signed-in session can open in this build. See [Access requests](doc:access-requests).

### Does the person get an email?

No email is sent. No invitation email, invite link, or token is generated in this build, so send the person the workspace URL yourself. The invitation also disappears on a full page reload.

### Why does the role toast print a name without spaces?

The toast and the denied-state tooltip print the internal role value, so `Strategic Planner `reads StrategicPlanner and Data Practitioner reads DataPractitioner. The row tag, the Change role list, and the invite dialog print the spaced label. Both name one role.

### I clicked a member's Role tag and got "No permission data available" — what is that?

The colored Role tag on a member's row is clickable and opens a role-permissions popover, but for this build's seeded roles it reads No permission data available. That is a mock surface, not a sign your permission data is missing. To see what a role can do, open the Manage Roles tab or the
[Permissions matrix](doc:permissions-matrix-reference).

### Someone is missing from the list where did they go?

Three things remove a row: each section shows at most 10 rows and hides the rest, deactivating deletes the row, and a full page reload restores the seeded list, dropping everyone you added. The Active list also hides the row whose email matches the signed-in user's, but those addresses never match the seeded members here, so it hides nobody.

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

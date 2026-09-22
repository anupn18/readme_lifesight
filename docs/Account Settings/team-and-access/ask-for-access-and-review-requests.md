---
title: Ask for access, and review requests
excerpt: >-
  Ask for Read or Manage access from the Access Restricted page, then approve or
  reject the request on Team > Access Requests.
deprecated: false
hidden: true
metadata:
  title: Ask for access, and review requests
  keywords:
    - Lifesight Requests
  robots: index
---
An access request asks for one module your role does not open; a Workspace Admin answers it. It starts on **Access Restricted** and lands on **Team > Access Requests**. This page covers both halves, plus the three unrelated controls also labeled **Request Access**.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Everyone can raise a request.
  **Approve or reject:** Workspace Admin only (`team.edit_permissions`). Every other role sees the full list with **Approve** and **Reject** (greyed) and the tooltip `Your role (<Role>) cannot edit permissions. Ask a workspace admin for access.`
</Callout>

## How a request travels

A disabled module opens **Access Restricted**, where **Request Access** creates a pending request that a Workspace Admin approves or rejects.

<Tabs>
  <Tab title="If you hit Access Restricted">
    A module your role cannot open still appears, dimmed, and opens the **Access Restricted page** instead. **Data, Profiles, Segments, and Config** sit in the Hub dropdown at the bottom of the sidebar, and every other module sits in the sidebar itself.
  </Tab>

  <Tab title="If you're a Workspace Admin">
    Requests land on **Team > Access Requests**, whose tab label carries an amber badge.
  </Tab>
</Tabs>

## Request access to a module

<Callout icon="📘" theme="info">
  ### **Role:** Everyone. Nothing in this dialog is gated.
</Callout>

1. In the sidebar or **Hub** dropdown, select the greyed module.
2. On **Access Restricted**, select **Request Access**.
3. Select **Read access** or **Manage access**.
4. Optional: add a reason in **Why do you need this access? (optional)**.
5. Select **Send request**.

**Send request** stays disabled until you select a card and reads **Sending…** while it works. On success the toast `Access request sent to your admin` appears, the dialog closes, and your name shows under **PENDING** on **Team > Access Requests**. If it reads `Failed to send request. Please try again.`, return to step 5.

Sending also raises the notification `Access request from <Name>` in the Notification pannel under the **Access** category, linking to **Team > Access Requests**.

## Review a request and decide who gets access

<Callout icon="📘" theme="info">
  ### **Role:** Workspace Admin&#x20;
</Callout>

1. In the sidebar, open the user menu and select **Team**.
2. Select the **Access Requests** tab.
3. Under **PENDING**, find the request by the person's name and the line `<Permission> · <Module>`.
4. Select **Approve**.
5. In `Approve access request?`, read which role the person moves onto. If it names no role, the requester has no matching **Manage Team** record and approving changes no role.
6. Select **Approve**.

To decline instead, select Reject at **step 4**. There is no confirmation dialog, and the card moves to **REVIEWED&#x20;**&#x61;t once.

**You're done when:**

- An approval shows the toast Access granted to <Name>. When a **Manage Team** record matched, it carries the description Created role "<Role>". or Assigned existing role "<Role>".
- The card sits under **REVIEWED**, reading Approved by WorkspaceAdmin.

### **What an approval changes**

An approval shows the toast Access granted to <Name>. When a **Manage Team** record matched, the toast adds Created role "<Role>". or Assigned existing role "<Role>". The card then moves to **REVIEWED**, reading `Approved by WorkspaceAdmin`. A rejection shows Request rejected, and the card reads` Rejected by WorkspaceAdmin`. Every review is recorded as `WorkspaceAdmin,` whoever performed it.

Approving builds a custom role named {Base role} + {Module} that keeps everything the person's current role allows and adds the requested module. For example, Executive plus Data becomes `Executive + Data`. The person's record on Manage Team moves onto that role. A second approval extends the name, as in `Executive + Data + Config`. When the requester matches no Manage Team record, no role is generated, no member record changes, and the toast carries no description. The generated role lives in the browser tab you approved from.

Approving also records a permission grant on the server, which any admin can read under **Team > Manage Team > Edit Permissions** from any browser.

If the toast reads` Failed to approve request,` the approval did not go through. This usually means the request was already reviewed elsewhere, but it can also mean the server is unreachable. Return to step 2 and re-read the list.`  Failed to reject request  `works the same way.

| Option        | Tag      | What it asks for                                       |
| ------------- | -------- | ------------------------------------------------------ |
| Read access   | `READ`   | `View {Module} — browse data, dashboards, and reports` |
| Manage access | `MANAGE` | `Edit and configure {Module} — includes read access`   |

A third tag, `ACTION`, exists on request cards for individual buttons, but the dialog never offers one — only these two are requestable.

## FAQ

**My request was approved. Why do I still see Access Restricted?**

An approval moves your member record onto a new role and records a permission grant, but a signed-in session keeps the role it was given at sign-in. Nothing re-reads either when you open a module, so it stays closed. See [What's live in this build](doc:whats-live-in-this-build).

**Should I request access or ask for a different role?**

Request access when your role fits your job and you need one extra module. Ask for a role change when the job changed and several modules are wrong. An approval adds one module to what you have; a role change replaces the whole set.

**Why does every reviewed request say WorkspaceAdmin?**

Every review is recorded as `WorkspaceAdmin`, whoever pressed the button, so **REVIEWED** cards read `Approved by WorkspaceAdmin` or `Rejected by WorkspaceAdmin`. The actual admin's name is not stored anywhere you can read.

**Does the requester hear about my decision?**

No message reaches the requester. The bell notification fires when a request is raised, not when it is reviewed, so tell the person yourself. This matters most after a rejection, since thei&#x72;**&#x20;Access Restricted** page looks the same either way. The seeded Access request approved notification everyone sees is a demo, not a reply to anything you sent.

**Can I withdraw a request I sent?**

A request cannot be withdrawn, edited or cancelled from your side, and it does not expire. A second request for the same module creates a second card, not a replacement. Ask a Workspace Admin to reject any you no longer need.

**The Access Requests tab is empty. Where did the requests go?**

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

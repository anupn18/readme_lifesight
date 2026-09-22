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
An access request lets you ask for one module your role doesn't open, so you can get what you need without changing your whole role. A Workspace Admin reviews and answers it. Requests start on the **Access Restricted** screen and land in **Team > Access Requests**. This page covers both sides: raising a request and reviewing one.

**Who can do this**

- **Raise a request:** everyone.
- **Approve or reject:** Workspace Admin only. Every other role sees the full list, with **Approve** and **Reject** dimmed and the tooltip "Your role (<Role>) cannot edit permissions. Ask a workspace admin for access."

## How a request works

A module your role can't open opens **Access Restricted**, where **Request Access** creates a pending request. A Workspace Admin then approves or rejects it.

**If you see Access Restricted**

A module your role can't open still appears, dimmed, and opens the **Access Restricted** screen instead. **Data**, **Profiles**, **Segments**, and **Config** sit in the **Hub** dropdown at the bottom of the sidebar. Every other module sits in the sidebar itself.

**If you're a Workspace Admin**

Requests land in **Team > Access Requests**, which shows an amber badge when requests are waiting.

## Request access to a module

**Role:** everyone

1. In the sidebar or **Hub** dropdown, select the dimmed module.
2. On **Access Restricted**, select **Request Access**.
3. Select **Read access** or **Manage access**.
4. Optional: explain what you need it for in **Why do you need this access? (optional)**. A clear reason helps your admin decide faster.
5. Select **Send request**.

**Choosing the right access level**

| Option        | Tag    | What it asks for                                    |
| ------------- | ------ | --------------------------------------------------- |
| Read access   | READ   | View <module>: browse data, dashboards, and reports |
| Manage access | MANAGE | Edit and configure <module>, including read access  |

Only these two levels can be requested. Request cards can also show an ACTION tag for individual buttons, but those can't be requested from the dialog.

**What happens next**

**Send request** stays unavailable until you select an access level, and reads **Sending…** while it works. When it succeeds:

- A confirmation appears: "Access request sent to your admin."
- The dialog closes.
- Your name appears under **PENDING** in **Team > Access Requests**.
- Admins receive a notification, "Access request from <Name>," under the **Access** category in the notification panel, linking to **Team > Access Requests**.

If you see "Failed to send request. Please try again.", select **Send request** again.

## Review a request

**Role:** Workspace Admin

1. In the sidebar, open the user menu and select **Team**.
2. Select **Access Requests**.
3. Under **PENDING**, find the request by the person's name and the line "<Permission> · <Module>."
4. Select **Approve**.
5. In **Approve access request?**, check which role the person will move onto. If no role is named, the requester has no matching **Manage Team** record, and approving won't change any role.
6. Select **Approve**.

**To reject a request**

Select **Reject** at step 4 instead. There is no confirmation, and the card moves to **REVIEWED** immediately.

**You're done when:**

- A confirmation appears: "Access granted to <Name>." When a **Manage Team** record matched, it adds "Created role "<Role>"." or "Assigned existing role "<Role>"."
- The card sits under **REVIEWED**, reading "Approved by WorkspaceAdmin."

**What an approval changes**

Approving creates a custom role named after the person's current role plus the requested module. It keeps everything their current role allows and adds the new module. For example, an Executive requesting Data becomes **Executive + Data**, and the person's **Manage Team** record moves onto that role. A second approval extends the name, such as **Executive + Data + Config**.

- If the requester has no matching **Manage Team** record, no role is created, no member record changes, and the confirmation has no extra description.
- The generated role is available in the browser tab you approved from.
- Approving also records a permission grant that any admin can view under **Team > Manage Team > Edit Permissions**, from any browser.

**What a rejection shows**

A confirmation appears: "Request rejected," and the card reads "Rejected by WorkspaceAdmin."

Every review is recorded as "WorkspaceAdmin," whoever performed it.

**If a review fails**

If you see "Failed to approve request" or "Failed to reject request," the review didn't go through. This usually means the request was already reviewed elsewhere, but it can also mean the service is unreachable. Reopen **Access Requests** and check the list again.

***

## Frequently Asked Questions

**Who can approve or reject requests?**
Only a Workspace Admin. Other roles can view every request, but **Approve** and **Reject** are dimmed.

**Should I request access or ask for a different role?**
Request access when your role fits your job and you need one extra module. Ask for a role change when your job has changed and several modules no longer fit. An approval adds one module to what you have; a role change replaces the whole set.

**Can I request access to a specific button or action?**
No. You can request **Read access** or **Manage access** to a module, but not individual actions.

**My request was approved. Why do I still see Access Restricted?**
In the current release, a signed-in session keeps the access of the role it had at sign-in, so the module may stay closed after approval. See **What's live in this build**.

**Will the requester be notified of my decision?**
No notification is sent to the requester. Admins are notified when a request is raised, not when it is reviewed. Let the person know yourself, especially after a rejection, since their **Access Restricted** screen looks the same either way.

**Why does every reviewed request say WorkspaceAdmin?**
Every review is recorded as "WorkspaceAdmin," whoever made the decision. The individual admin's name isn't shown.

**Can I withdraw a request I sent?**
No. Requests can't be withdrawn, edited, or canceled, and they don't expire. Sending a second request for the same module creates a second card rather than replacing the first. Ask a Workspace Admin to reject any you no longer need.

**What happens if the same person requests the same module twice?**
Each request creates its own card. Approve one and reject the duplicate.

**Can a reviewed request be reopened?**
No. If the person still needs access, ask them to raise a new request.

**The Access Requests list is empty. Where did the requests go?**
When there are no requests, the list shows "No pending requests" and "No reviewed requests yet." In the current release, requests can also be cleared when the service restarts, including reviewed ones.

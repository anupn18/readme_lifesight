---
title: '[4.0][ReadyForQA]Set up your profile and preferences'
excerpt: >-
  Set your persona, hide sidebar modules you never open, and change your profile
  photo, from Settings > Preferences and Edit Profile.
deprecated: false
hidden: true
metadata:
  robots: index
---
Your profile and preferences decide how Lifesight looks and behaves for you. Pick the persona that matches how you work and Lifesight puts the right things first in your Cockpit, Ask answers, and alerts. Hide the modules you never open and your sidebar carries only what you use.<br /><br />Set them on the **Preferences** >> **Settings** >> **Edit Profile**.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Everyone, no control on **Preferences** or **Edit Profile** is role-gated
  **Where:** Sidebar user menu > **Settings** > **Preferences**
  **Time:** About 2 minutes.
</Callout>

## Before you start

- You are working in the workspace you want these preferences to apply to. Your persona, hidden modules, and theme are stored in that workspace, so they will not follow you to a different workspace or device.

## Edit your profile

1. On the **Preferences tab,** find the Your profile card.
2. Select **Edit profile**, the pencil button.
3. Make your changes on the **Edit Profile page**, headed Update your `profile photo, persona, and password.`
4. Select **Save changes.**

The toast **Profile updated** appears. Back to Settings returns you to the Preferences tab.

The page holds three rows: **Profile photo, Persona, and Password.**

Profile photo offers **Upload, Replace, and Remove profile photo**, described as `shown on your profile card and anywhere your account appears`. Treat the photo as a preview only in this build. It shows in the tab you uploaded it in and is not kept after a reload.

<Callout icon="📘" theme="info">
  `We'll email a reset link to <email>. It expires in 1 hour.` It opens a confirmation dialog, `Send a password reset link?`; **Send reset link** sends it. The row then reports `Reset link sent` and the button reads **Send again**, but nothing is delivered; the server only writes the link to its own console.
</Callout>

## Choose the persona that matches how you work

Your persona tailors your Cockpit, Ask answers, and alerts to the work you actually do. It does not change what you can open.

1. On **Edit Profile**, open the **Persona** select.
2. Select a persona.
3. Select **Save changes**.

The toast `Profile updated` appears, and the label under your name in the sidebar
user menu changes to it.

`Persona personalizes your experience across the platform`. Persona is not access control, it changes what those put first, not which modules you can open. Role decides that, see [Roles: what each one opens, and what it can do](doc:roles-and-permissions).

| Persona             | The starting persona for |
| ------------------- | ------------------------ |
| Measurement Analyst | Marketing Scientist      |
| Growth Marketer     | No role starts here      |
| Media Planner       | Strategic Planner        |
| Marketing Ops       | Data Practitioner        |
| Marketing Leader    | Executive                |
| Generalist          | Workspace Admin, Viewer  |

Those six are the whole list, in select order. Until you pick one, Lifesight uses your role's starting persona.

## Hide modules you don't use

1. In the sidebar, open the user menu and select **Settings**.
2. Select the **Preferences** tab.
3. Under **Customize Menu**, find the module's row.
4. In the **Action** column, select the eye button on that row.
5. Select **Save changes** in the footer.

![](https://files.readme.io/4cb25298aa26d348bf4f3a94d077a93fcc2db500760de4f58195306f4e8e633f-Screenshot_2026-09-21_at_7.31.04_AM.png)

The toast `Capabilities saved` appears, and the sidebar drops the module **Customize Menu** is introduced as `Toggle the visibility of modules you have access to. Hidden modules won't appear in your sidebar.`

See the FAQ if a module returns.

## Ask for access to a module your role can't open

<br />

Below **Customize Menu**, a second table headed Modules not included in your current role. **Request access&#x20;**&#x74;o enable them lists the modules outside your role, each with a Request Access button. A Workspace Admin never sees this table, because no module is closed to that role.

To raise a request that reaches an admin, open the module from the sidebar and use the dialog on the Access Restricted screen.&#x20;

- Find the module's row and select **Request Access.**
- In the **Request Access:&#x20;**<Module> dialog, choose Read-only or Manage / Edit.
- If the module has a **Special Actions** checklist, tick the actions you need. The list is dimmed under **Read-only** and tickable unde&#x72;**&#x20;Manage / Edit.**
- Select **Submit Request.**

## FAQ

### Should I hide a module or request access to it?

Hide a module you can open but never use, and it leaves your sidebar. Request access to a module your role cannot open. Those are grayed in the sidebar, show Access Restricted when selected, and appear under Additional Capabilities rather than Customize Menu.

### Does my persona change what I can open?

No. Persona tailors your Cockpit, Ask answers, and alerts to how you work. Your role opens modules and enables buttons.

### Why does my profile card show someone else's name?

The card reads from a demo directory whose addresses never match sign-in addresses, so everyone sees a demo Workspace Admin record and its role pill. The persona line always reads Generalist, because the demo persona is not one of the six and collapses to the default. Your real name, persona, and role are in the sidebar user menu.

### Why are my hidden modules back?

They are stored in the browser you saved them in. A different browser, device, private window, or cleared site data all start from every module visible. Hide them again on Settings > Preferences > Customize Menu.

### I asked for a password reset link and nothing arrived

No password reset email is sent in this build, whichever screen you ask from. The link goes nowhere and your current password keeps working. See [Find your symptom](doc:troubleshooting).

## Related

<Cards columns="2">
  <Card title="Workspace settings" href="doc:workspace-settings" icon="fa-sliders">
    The settings that apply to the whole workspace, not only you.
  </Card>

  <Card title="Ask for access, and review requests" href="doc:access-requests" icon="fa-key">
    The request that actually reaches an admin.
  </Card>
</Cards>

## Agent card

```yaml agent
task: settings-personal-preferences
title: Your profile and preferences
type: howto
surface: Settings
page: https://docs.lifesight.io/docs/your-profile-and-preferences
last_verified: 2026-09-13

state: browser
persistence: browser_local
state_note: >
  Persona, hidden sidebar modules and theme are written to this browser's
  localStorage. They survive a reload in this browser and are absent in any other
  browser or on any other device; no server record holds them.

requires_role: []
requires_rights: []
denied_ux: >
  None. Every role, Viewer included, can open Settings > Preferences and
  Edit Profile, and no control on either page is gated or dimmed.

entry_point: "Sidebar user menu > Settings > Preferences"
url: "/settings?tab=preferences"
preconditions:
  - Signed in to Lifesight.
  - Acting in the browser the preferences should apply to.

ui_strings:
  tabs: ["Workspace", "Preferences"]
  profile_section: "Your profile"
  edit_profile_button: "Edit profile"
  profile_page_title: "Edit Profile"
  profile_page_subtitle: "Update your profile photo, persona, and password."
  back: "Back to Settings"
  profile_rows: ["Profile photo", "Persona", "Password"]
  photo_description: "Shown on your profile card and anywhere your account appears."
  photo_buttons: ["Upload", "Replace", "Remove profile photo"]
  persona_description: "Tailors your Cockpit, Ask answers, and alerts to how you work."
  persona_tooltip: "Persona personalizes your experience across the platform"
  persona_placeholder: "Select persona"
  persona_options:
    [
      "Measurement Analyst",
      "Growth Marketer",
      "Media Planner",
      "Marketing Ops",
      "Marketing Leader",
      "Generalist",
    ]
  password_status: "We'll email a reset link to <email>. It expires in 1 hour."
  password_button: "Reset password"
  customize_menu: "Customize Menu"
  customize_menu_description: "Toggle the visibility of modules you have access to. Hidden modules won't appear in your sidebar."
  customize_menu_columns: ["Capability", "Description", "Action"]
  customize_menu_toggle: "Toggle <Module> visibility"
  customize_menu_empty: "No customizable modules."
  additional_capabilities: "Additional Capabilities"
  additional_capabilities_description: "Modules not included in your current role. Request access to enable them."
  request_access: "Request Access"
  requested: "Requested"
  request_dialog_title: "Request Access: <Module>"
  request_levels: ["Read-only", "Manage / Edit"]
  request_submit: "Submit Request"
  footer: "You have unsaved changes"
  discard: "Discard changes"
  save: "Save changes"
  theme_button: "Toggle theme"

procedures:
  - id: choose-your-persona
    goal: Set the persona that tailors the Cockpit, Ask and alerts.
    steps:
      - 'On "Edit Profile", open the "Persona" select.'
      - 'Select a persona.'
      - 'Select "Save changes".'
    expect: 'Toast "Profile updated".'
    verify: 'The label under the name in the sidebar user menu reads the persona selected in step 2.'
    on_fail: 'Select "Discard changes" and repeat from step 1.'
    reversible: true
    undo: 'Repeat with the previous persona.'
  - id: hide-modules-you-dont-use
    goal: Remove a module you can open from your own sidebar.
    steps:
      - 'In the sidebar, open the user menu and select "Settings".'
      - 'Select the "Preferences" tab.'
      - 'Under "Customize Menu", find the module''s row.'
      - 'In the "Action" column, select the eye button on that row.'
      - 'Select "Save changes" in the footer.'
    expect: 'Toast "Capabilities saved".'
    verify: 'The sidebar no longer lists the module, within about 1 second. System modules disappear from the "Hub" dropdown instead.'
    on_fail: 'If no footer appeared, the toggle did not register — return to step 4.'
    reversible: true
    undo: 'Select the eye button again and save. Do not use "Discard changes": it also resets the brand kit to factory defaults.'

limits:
  - '"Customize Menu" lists only modules the role can open; every other module is listed under "Additional Capabilities".'
  - 'Viewer is the exception: the Settings page splits the two tables as if the signed-in Viewer were an Executive, so modules a Viewer can open from the sidebar appear under "Additional Capabilities" and are missing from "Customize Menu".'
  - A Workspace Admin sees no "Additional Capabilities" table, because no module is closed to that role.
  - The sidebar picks up a saved menu change within about 1 second.
  - The persona list holds exactly six options and cannot be extended.
  - Modules released after preferences were saved appear visible rather than hidden.
  - There is no theme control on the Settings page.

agent_rules:
  - Do not tell the user the profile photo was uploaded or saved. It is a preview in one browser tab and is lost on reload.
  - Do not tell the user a persona or hidden-module choice follows them to another browser or device. It does not.
  - Do not present "Request Access" under "Additional Capabilities" as raising a request. Send the user to the Access Restricted screen's dialog instead.
  - Do not tell the user a password reset email was sent from the "Password" row. None is sent, however confidently the row and its toast report "Reset link sent".
  - Do not tell a Viewer that "Additional Capabilities" lists what their role cannot open. For a Viewer that table is computed as if they were an Executive; a Viewer can open every module.
  - Do not treat persona as access. Role decides what opens; persona only reorders what is foregrounded.
  - Do not advise "Discard changes" to undo a menu toggle. It also resets the brand kit to factory defaults.

related:
  [
    workspace-settings,
    notifications,
    access-requests,
    roles-and-permissions,
    whats-live-in-this-build,
  ]
```

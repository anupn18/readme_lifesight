---
title: '[4.0][WIP]Your profile and preferences'
excerpt: >-
  Set your persona, hide sidebar modules you never open, and change your profile
  photo, from Settings > Preferences and Edit Profile.
deprecated: false
hidden: true
metadata:
  robots: index
---
Your persona, profile photo, sidebar modules, and theme are personal — nobody
else sees them. Set them on the **Preferences** tab of **Settings** and the
**Edit Profile** page one click beyond it.

<Callout icon="📘" theme="info">
  ### Who can do this

  **Role:** Everyone — no control on **Preferences** or **Edit Profile** is role-gated
  **Where:** Sidebar user menu > **Settings** > **Preferences**
  **Time:** About 2 minutes.
</Callout>

## Before you start

- You are signed in to Lifesight.

## Edit your profile

1. In the sidebar, open the user menu and select **Settings**.
2. Select the **Preferences** tab.
3. On the **Your profile** card, select **Edit profile** — the pencil button.
4. Select **Save changes**.

The toast `Profile updated` appears.

**Edit Profile** is headed `Update your profile photo, persona, and password.`
**Back to Settings** returns you to the **Preferences** tab.

The **Password** row offers **Reset password**, promising
`We'll email a reset link to <email>. It expires in 1 hour.` It opens a
confirmation dialog, `Send a password reset link?`; **Send reset link** sends it.
The row then reports `Reset link sent` and the button reads **Send again** — but
nothing is delivered; the server only writes the link to its own console.

## Choose your persona

1. On **Edit Profile**, open the **Persona** select.
2. Select a persona.
3. Select **Save changes**.

The toast `Profile updated` appears, and the label under your name in the sidebar
user menu changes to it.

`Persona personalizes your experience across the platform`. Persona is not access control — it changes what those put first, not which modules you can open. Role decides that — see [Roles: what each one opens, and what it can do](doc:roles-and-permissions).

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

The toast `Capabilities saved` appears, and the sidebar drops the module **Customize Menu** is introduced as `Toggle the visibility of modules you have access to. Hidden modules won't appear in your sidebar.`


See the FAQ if a module returns.

## Additional Capabilities

Below **Customize Menu**, a second table headed
`Modules not included in your current role. Request access to enable them.` gives each module your role cannot open a **Request Access** button; a Workspace Admin never sees this table. The button opens the dialog `Request Access: <Module>`, offering **Read-only** and **Manage / Edit**. For modules with special actions, a **Special Actions** checklist appears below — dimmed under **Read-only**, tickable under **Manage / Edit** — and ticked actions are appended to the toast.<br />
**Submit Request** shows a toast such as `Access requested for <Module>: Read` and leaves the row reading **Requested**.&#x20;

## FAQ

### Should I hide a module or request access to it?

Hide a module you can open but never use — it leaves your sidebar. Request access
to a module your role cannot open: those are greyed in the sidebar, show
**Access Restricted** when selected, and appear under **Additional Capabilities**,
not **Customize Menu**. A Viewer is the exception — that table is wrong here.

### Does my persona change what I can open?

Persona changes nothing about what you can open — it tailors the Cockpit, Ask
answers and alerts to how you work. Your role opens modules and enables buttons.

### Why does my profile card show someone else's name?

The card reads from a demo directory whose addresses never match sign-in
addresses, so everyone sees a demo Workspace Admin record and its role pill. The
persona line always reads **Generalist** — the demo persona isn't
one of the six, so it collapses to the default. Your real name, persona and role
are in the sidebar user menu.

### Why are my hidden modules back?

Hidden modules are stored in the browser you saved them in. A different browser,
device, private window or cleared site data all start from every module visible,
and newly released modules arrive visible. Hide them again on
**Settings > Preferences > Customize Menu**.

### I asked for a password reset link and nothing arrived

No password reset email is sent in this build, whichever screen you ask from. The
link is generated and goes nowhere, and your current password keeps working. See
[Find your symptom](doc:troubleshooting).

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
app_build: "ls4x@feature/LS4X-155"

state: browser
persistence: browser_local
state_note: >
  Persona, hidden sidebar modules and theme are written to this browser's
  localStorage. They survive a reload in this browser and are absent in any other
  browser or on any other device; no server record holds them. The profile photo
  is weaker still: it is a preview object URL held in the page and is gone on
  reload, never uploaded, and never shown on the profile card or in the sidebar,
  both of which draw initials. "Request Access" under "Additional Capabilities"
  is a preview: it shows a toast, sets a local "Requested" pill, creates no
  record and resets on reload. The "Password" row mints a reset link that is
  never delivered to anyone.

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
  - id: edit-your-profile
    goal: Open Edit Profile and set a profile photo.
    steps:
      - 'In the sidebar, open the user menu and select "Settings".'
      - 'Select the "Preferences" tab.'
      - 'On the "Your profile" card, select "Edit profile" — the pencil button.'
      - 'In the "Profile photo" row, select "Upload", then choose an image file.'
      - 'Select "Save changes".'
    expect: 'Toast "Profile updated" with description "Your profile has been successfully updated."'
    verify: 'The "Profile photo" row shows the image, "Upload" now reads "Replace", and a "Remove profile photo" button sits beside it.'
    on_fail: 'The footer only appears once something changed. If no footer appeared, no file was chosen — return to step 4.'
    reversible: true
    undo: 'Select "Remove profile photo", then "Save changes". A reload also clears it.'
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
  - id: switch-between-light-and-dark
    goal: Change the theme for this browser.
    steps:
      - 'Select "Toggle theme" in the header, or press "d" while focus is outside a text field.'
    expect: 'The interface switches between dark and light immediately.'
    verify: 'The header button shows a sun in light theme and a moon in dark theme.'
    reversible: true
    undo: 'Select "Toggle theme" again.'

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

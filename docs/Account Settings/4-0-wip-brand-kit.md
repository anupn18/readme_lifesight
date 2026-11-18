---
title: Brand Kit
excerpt: >-
  Settings > Brand Kit puts your brand's name, logo, colors and fonts on your
  workspace's live dashboards and the visuals in Ask Lifesight.
deprecated: false
hidden: true
metadata:
  title: Set up your workspace's Brand Kit in Lifesight
  description: >-
    Settings > Brand Kit puts your brand's name, logo, colors and fonts on your
    workspace's live dashboards and the visuals in Ask Lifesight.
  keywords:
    - Lifesight
    - Brand Kit
    - Settings
    - Dashboards
  robots: noindex
---
Your **brand kit** makes your live dashboards look like your brand. It holds your brand's name, logo, colors and fonts, and Lifesight uses them on every live dashboard in the workspace and on the visuals in Ask Lifesight. The rest of the app keeps Lifesight's own look.

Each workspace has one brand kit, so everything the team builds shares the same look. Set it up once, and every dashboard picks it up.

**Who can do this**

- **Role:** everyone can open **Brand Kit** and see the kit. Changing it needs the **Configure Brand Kit** right, which Workspace Admins have. If you can't change it, the kit shows: "Only workspace admins can change the brand kit."
- **Where:** sidebar user menu > **Settings** > **Brand Kit**, under **Workspace**.

To give the right to another role, see [Create a custom role](doc:creating-a-custom-role) and the [Permission Matrix](doc:permission-matrix).

***

## Find your brand kit

1. In the sidebar, open the user menu and select **Settings**.
2. Under **Workspace**, select **Brand Kit**.

The **Default brand kit** card shows the kit at a glance: the logo (or the brand's first letter until a logo is added), the brand name, the heading font, whether charts use your own colors, and a row of your main colors. Select **Open** to see or change it, and **All brand kits** to come back.

![Settings > Brand Kit, with the Default brand kit card](https://files.readme.io/02c170b654fb3ac477b077bcc2b2406190bb7b5c97f0b508c91dc340fec36564-17-brandkit-tab.png)

If nobody has set the kit up yet, the card reads "Not set up yet, so dashboards use Lifesight's look".

***

## Set up your brand kit

**Role:** Workspace Admin

Open the kit, fill in what you need, and select **Save brand kit**. Every field is optional: anything you leave empty keeps Lifesight's own.

![The brand kit form: brand name, logo and colors](https://files.readme.io/a2116186b5a88593a95024c194ec02588a720588780b871756ea866ee06d92c1-18-brandkit-form.png)

### Brand name and logo

| Field          | What to enter                                                                                                                                         |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Brand name** | Your brand's name. It shows with the logo beside each dashboard's title.                                                                               |
| **Logo**       | A PNG or SVG file of 1 MB or less, uploaded for **Light** surfaces and, if you have one, for **Dark** surfaces. Without a dark version, the light one is used on dark surfaces. A dark logo needs a light one too. |

### Colors

**Colours** has six colors, each with a **Light** and a **Dark** version for the light and dark themes:

| Color                                   | Where it's used                                          |
| --------------------------------------- | -------------------------------------------------------- |
| **Primary**, **Secondary**, **Accent**  | Your brand colors, on buttons, highlights and details    |
| **Page**                                | The dashboard's background                               |
| **Card**                                | The background of each tile                              |
| **Text**                                | Titles, figures and body text                            |

Lifesight checks that every color can be read on the surface behind it. If one can't, it's adjusted when you save, and **Adjusted for contrast** shows the color you gave beside the color dashboards will use. If no adjustment can make a color readable, the kit isn't saved and you're asked to choose a color further from its background.

### Chart colors

**Chart series** sets the colors charts give their series, in order, each with a **Light** and a **Dark** version. Charts have twelve series colors: nine are yours to set, and three stay fixed so **TikTok**, **Meta** and **Google** keep their own colors everywhere.

![The rest of the brand kit form: chart series, heading and body fonts, corner radius, and Save brand kit](https://files.readme.io/2309397759e19bd58e96c9e7f275beaa703dbfe7e6757fc35b4e8ae8ee4ffae1-19-brandkit-form-fonts.png)

### Fonts

| Field            | Used for                                           |
| ---------------- | -------------------------------------------------- |
| **Heading font** | Dashboard titles and headline figures              |
| **Body font**    | Everything else on dashboards and in chat visuals  |

For each one, pick **Sans-serif (Instrument Sans)**, **Serif (Source Serif 4)** or **Monospace (Geist Mono)** from the list, or use your own font:

1. Select **Upload** beside the font and choose a TrueType or OpenType file of 5 MB or less.
2. Lifesight measures the font against the dashboard's layout. A font that sets text too wide for the layout is refused, so choose a narrower one.
3. Confirm that your workspace holds a licence to use the font on its dashboards and documents.
4. Select **Use this font**.

If the font's digits aren't all the same width, headline figures keep Lifesight's own figure font so numbers stay aligned.

### Corner radius

**Corner radius** sets how round cards and controls are, from 0 to 24 px.

### Save your changes

Select **Save brand kit**. A message confirms "Brand kit saved", and dashboards use the new kit the next time they open. To undo everything you changed since the last save, select **Discard changes**.

<Callout icon="📘" theme="info">
  **Note:** If someone else saves the brand kit while you're editing it, you're told before anything is overwritten. Select **Load their version** to see their changes, then make yours again.
</Callout>

***

## See your brand on a dashboard

Open any live dashboard in the workspace. Your logo and brand name sit beside its title, the page and tiles use your colors, titles and figures use your heading font, and charts use your chart colors. See [Live Artifacts](doc:4-0-wip-live-artifacts).

***

## Frequently Asked Questions

**What does the brand kit change?**
Your workspace's live dashboards and the visuals in Ask Lifesight. The rest of the app keeps Lifesight's own look.

**Can a workspace have more than one brand kit?**
No. Each workspace has one brand kit, used by every dashboard in it.

**Who can change the brand kit?**
Workspace Admins, and any custom role given the **Configure Brand Kit** right. Everyone else can open it and see it.

**Do I have to fill in every field?**
No. Anything you leave empty keeps Lifesight's own look.

**Why did my color change after I saved?**
It wasn't readable enough on the surface behind it, so Lifesight adjusted it until it was. **Adjusted for contrast** shows the color you gave and the color dashboards use.

**Why can't I change the TikTok, Meta and Google chart colors?**
Those three keep their own colors on every chart, so the platforms are easy to spot. The other nine chart colors are yours to set.

**Which logo files can I use?**
PNG or SVG, up to 1 MB. Upload a light version, and a dark version if you have one.

**Which font files can I upload?**
TrueType or OpenType files up to 5 MB, as long as your workspace holds a licence to use the font and it fits the dashboard layout.

**When do dashboards show my changes?**
The next time each dashboard opens.

**Do I need to set the kit up for each dashboard?**
No. One kit covers every live dashboard in the workspace.

## Related pages

<Cards columns={2}>
  <Card title="Artifacts" href="https://docs.lifesight.io/docs/4-0-wip-artifacts" icon="🗂️">
    The library, folders, uploads and sharing.
  </Card>

  <Card title="Live Artifacts" href="https://docs.lifesight.io/docs/4-0-wip-live-artifacts" icon="📊">
    Dashboards that read your workspace data every time they open.
  </Card>
</Cards>

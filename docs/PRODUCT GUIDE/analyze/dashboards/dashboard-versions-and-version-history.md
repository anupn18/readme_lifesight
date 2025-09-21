---
title: Dashboard versions and version history
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Dashboards have versions. The default versions are Published and Draft, and you can add new custom versions called "tagged versions". 

Dashboard version history contains a list of all previously published versions of a Dashboard and any pending draft changes. Each published version includes a detailed list of changes, called the edit history. You can use the version and edit history to review drafted changes, compare or revert to older published versions, identify who on your team made a specific edit or set of changes, or identify which version is tagged with a specific version tag. There is no limit to the retention period of Dashboard version history.

## Requirements

* Dashboard version history, including edit history and any edits to the current draft, is only available for users with Can Edit permission on a Dashboard.
* Only users with Can Edit permission can restore old versions and changes to a Dashboard.

Edit history is not available for changes made before December 13, 2022. Beginning on December 13, 2022, all organizations with Live Edit enabled track edits in the edit history. Edits made before Live Edit is enabled remain untracked.

## About dashboards version

When you open a Dashboard, the current version is listed in the Dashboard header:

* If you're viewing a published Dashboard, the version is PUBLISHED.
* If you're viewing a tagged version, the name of the version tag is shown.
* If you open the Dashboard for editing, the version is DRAFT.

A Dashboard can have one of the following versions:

* Draft: While you are editing a Dashboard, it is in draft mode and the changes are visible only to you and others currently editing the Dashboard.
* Published: To make changes visible to others with view or explore access to the Dashboard, you publish it.
* Tagged: If you want to have a read-only version of a Dashboard available to specific users or for a specific purpose, you can apply a tag to a specific Dashboard version. For example, you may tag a Dashboard as "Development" or "Production".

## Open version history for a dashboard

When you make changes to a Dashboard, the changes appear in the version history. When you publish a version, the version history updates.

You must have Can Edit permissions on the Dashboard to view the version history.

1. Open a Dashboard.
2. Click the drop-down next to the document name, then select Version History. You can also select the name of the current version, then select View version history.\
   The version history panel opens and displays the latest version and its changes. Previously published versions are listed below, and the version corresponding to the currently published version is labeled Current.
3. Review the detailed edit history for a specific version by clicking the chevron next to the version timestamp, or see the Dashboard as it was for a specific version or change by selecting it.
4. To return to the latest version of the Dashboard, select Go back to the latest version.
5. To close the version history panel, click X.

## Restore a draft to a previous change or version

To return a Dashboard to a previously published version, or to a specific change in the Dashboard version history, restore a previous change or version to draft. Any changes made before you restore a previous version remain in the version history.

You must have Can Edit permissions on the Dashboard to restore a previous version or change in the version history.

### Restore a draft to a previously published version

To restore a draft to a previously published version, do the following:

1. Open the version history for a Dashboard.
2. Locate the previously published version that you want to restore.
3. Click  More, then select Restore version as draft. The change appears in the version history as a Restored version from with the timestamp of the version listed.
4. Make other changes as needed, or click Publish to publish the changes.

### Revert to a previous change in the version history

You can restore your Dashboard draft to a specific change in the edit history for a version or draft.

> 📘 If your Dashboard contains input tables and you restore your Dashboard to a previous change in the version history, the input table contents are not restored to that point in time and instead reflect the latest changes.

Instead, you can restore the published version closest to the specific change, and then restore the specific change.\
To revert your draft to a previous change in the edit history, do the following:

1. Open the version history for a Dashboard.
2. Locate the version that contains the change that you want to revert your draft to.
3. If needed, expand the edit history of the version, then locate and select the change.
4. In the Dashboard header, select Restore version as draft. The change appears in the version history as Restored from autosaved draft.
5. Make other changes as needed, or click Publish to publish the changes.

## Work with previously published versions

When reviewing the version history for a Dashboard, you can perform several actions on previously published versions. Select More to do any of the following:

* Select Restore version as a draft to restore the version as a draft. See Restore a draft to a previously published version.
* Select Edit name and description to change the name and description of a version. By default, a version is listed by timestamp.
* Select Save as a new Dashboard to save the version as a new Dashboard.
* Select the Copy link to copy a link to the previous Dashboard version. Only users with access to the Dashboard can view the link.
* Set a tag on the version.

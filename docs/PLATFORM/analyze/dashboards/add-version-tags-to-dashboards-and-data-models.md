---
title: Add version tags to Dashboards and data models
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
> 📘 Version tagging data models is a public beta feature that’s subject to quick, iterative changes. As a result, the latest product version may differ from the contents of this document.
>
> Tagging Dashboard versions are generally available.

Add a tag to a Dashboard or data model version to create a read-only view of that version of the document. You can then share the tagged version with another team for their exclusive use, use the tagged Dashboard version to support an embed, or implement tagged versions for version control as part of a development lifecycle for a Dashboard or data model.

Tagging a Dashboard or data model version effectively publishes the document version at that particular point in time, but lets you continue iterating on the source document in a typical draft and publish workflow, without affecting the tagged version. 

You can tag multiple versions of a Dashboard or data model, but you cannot have multiple versions of a document tagged with the same tag.

Admins can create and manage version tags, including creating protected tags that require an approval flow.

## Version tagging workflow

All Dashboards and data models have Draft and Published versions, and all changes made to a document are visible in the version history.

You can tag a specific document version to indicate something about the status of that document version. For example, tag a version of a Dashboard to indicate that the contents need to be reviewed for accuracy, or that it is ready to be used in production.

<Image align="center" src="https://files.readme.io/7083cafc918011bba8c173bf3f91b072bd5920985e451c21a10eab8328fc3227-4be75c3ec3cb8eaefd59cade127457cb1258bb6afa73e321f0aa15e50a019c95-version-tag-workflow.png" />

You can also version tag data model documents, and use a similar workflow to tag specific data model versions for testing or production use.

You can continue iterating on the draft version while the tagged version is being reviewed. Changes made to the untagged versions (draft and published) do not affect the tagged version.

<Image align="center" src="https://files.readme.io/22b1567bc5b79b980d08feafbbc5c3d78e7c1d40ecb38f4d00f1f1f4da097850-f2.png" />

<br />

### How version tagging affects datasets and data models

When you version tag a Dashboard that uses a dataset as the data source, a copy of the dataset version in use is created to use with the tagged Dashboard. The dataset associated with the tagged Dashboard no longer updates even if changes are made to the original dataset, effectively freezing the version of the dataset that was in use when the Dashboard version was tagged. The data source itself is not affected in any way by a version tag.

Dashboards that use a data model as the data source work differently. When you version tag a Dashboard that uses a data model as the data source, the Dashboard version is tagged, but the data model version is not. Any future changes made to the data model, such as adding new columns or changing the data type of an existing column, are synced with the versions of the Dashboard that depend on the data model.

If you want to "freeze" the data model used as the data source of a tagged version of a Dashboard, you can tag both the data model and the Dashboard and use the tagged data model as the data source for the tagged version of the Dashboard.

### Version tagging embedded Dashboards

If you embed your Dashboard, you can use version tags to manage promoting content between environments. For example, use "test" and "production" tags to help manage changes and protect the version that is used in production. You can then use a link directly to a tagged version in your embed.

If you want to integrate version tagging in Lifesight with the source control platforms already integrated with your development workflow, you can use the Lifesight REST API. 

### Version tagging and materialization

When you tag a version of your Dashboard that relies on a materialized data source, the tagged version might not use the materialized data source.

* Materialized dataset: The materialized dataset is not used by the tagged version of the Dashboard. Instead, the tagged version of the Dashboard relies on a copy of the dataset made when the tag was applied.
* Materialized data model: The materialized data model is used unless you use a tagged version of the data model, such as when swapping sources for the tagged Dashboard version. Tagged versions of data models cannot be materialized.

| Object            | Is materialized version used?       | Details                                                                                                                                                |
| :---------------- | :---------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dataset           | ❌ Materialized version is not used. | The tagged version of the Dashboard uses a copy of the dataset instead of the original dataset.                                                        |
| Data model        | ✅ Materialized version is used.     | The tagged version of the Dashboard uses the data model, remaining in sync with any changes made to the data model and using the materialized results. |
| Tagged data model | ❌ Materialized version is not used. | The tagged version of the Dashboard uses a tagged version of the data model, which cannot be materialized at this time.                                |

## Tag a Dashboard or data model version

You can tag a version of a Dashboard or a data model. When you tag a document, you create a read-only version of the document that you can then share with others or embed.

### User requirements

To tag a document version, the following must be true

* Your user is granted Can Edit permissions on the document.
* The account type assigned to your user is granted the Apply Tag and Create, edit, and publish Dashboards permissions.

Some tags might be protected and require additional permissions to set on a document. To set a protected tag, you must also be an admin or be granted access to set the protected tag. If you do not have access to set the protected tag, you can send a request for it to be added.

### Set a tag on a document

To set a tag on a document, follow these steps.

1. Open the document and locate the version that you want to tag:
   1. To tag the latest published version of the document, click the caret () next to the document name and select Tag this published version. If the document is in draft and has unpublished edits, you instead see Tag latest published version.
   2. To tag the latest draft of the document, while editing the document, select the caret () next to the document version and select Tag this version.
   3. To tag a specific version of the document, open the version history of the document by selecting the caret next to the document name > Version history, then locate the version you want to tag. Click  More > Set tag on this version.\
      The Set Tag on Version modal appears.
2. For Choose Tag, select a tag.

<Image align="left" src="https://files.readme.io/bc031280910b82052aa1ef9ccc735f04576394cabac74e3ca547c22955b9f1e5-97d7e8a-Screenshot_2024-05-29_at_9.12.41_AM.png" />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

If you choose a protected tag that you do not have permission to apply, you're prompted to send a request to approvers for the tag:

* For Why are you requesting to set this tag?, enter the message you want to include in the email request.
* Click Request Tag on Version.\
  Lifesight sends an email to members that can approve the request.

3. For a version tagged Dashboard, if you want to grant Can view permissions on the data sources used in the Dashboard, select the checkbox for Allow user to use data sources when they "Save as". If this checkbox is not selected, users can access the tagged version of the Dashboard without data.
4. If you want the tagged version of the document to use a different data source (whether a connection, database, table, or data model or dataset), select the checkbox for Swap sources of the tagged version.
5. If you want users that only have access to the tagged version of the document to open the tagged version by default, select the checkbox for Set this tag as default.
6. Click Set Tag.

### Set a default version tag for a document

When you apply a tag to a Dashboard or data model, you can set the tag as the default. The default tag determines what version of a document is displayed by default to a user who does not have access to the Published version. If a user does have access to the Published version, the Published version takes precedence over the default tag.

To remove a tag from a document version:

1. Open the document.
2. From the document header menu, select the caret  > Version history.\
   \[optional] To collapse the details changes for each version, select the caret next to the most recent version.
3. Locate the tagged version and select  More > Remove this tag. The tagged version is shown on the canvas when you remove the tag.

## Swap the source of a tagged Dashboard version

To swap the source of a tagged Dashboard version, for example to use a test data connection for a Dashboard tagged "testing" and swap to a production data connection for a Dashboard tagged "production", follow these steps. 

The steps are different if your Dashboard uses a data model for the data source or not:

* Swap the data model source used by a tagged Dashboard version.
* Swap the dataset or connection source used by a tagged Dashboard version.

### Swap the data model source used by a tagged Dashboard version

If your Dashboard uses a data model as the data source and you want the tagged Dashboard version to use a different data source than the published version, first tag the data model and swap the source of the tagged data model, then tag the Dashboard and use the tagged data model as the source.

By swapping the data connection source based on a tagged version of the data model, instead of the tagged version of the Dashboard directly, you can more easily manage and control access to data sources.

Tag the data model and swap the source

1. Open the data model for editing, then choose the version to tag:
   1. To tag the latest published version of the document, click the caret () next to the document name and select Tag this published version. If the document is in draft and has unpublished edits, you instead see Tag latest published version.
   2. To tag the latest draft of the document, while editing the document, select the caret () next to the document version and select Tag this version.
   3. To tag a specific version of the document, open the version history of the document by selecting the caret next to the document name > Version history, then locate the version you want to tag. Click  More > Set tag on this version.\
      The Set Tag on Version modal appears.
2. For Choose Tag, choose a tag to apply to the data model. For clarity, choose the same tag that you plan to use with the Dashboard.
3. Select the checkbox for Swap sources of the tagged version.
4. Click Set Tag.
5. In the Modify sources modal, in Sources of tagged data model, select a new data source to use for the tagged version.
6. Select Swap and Tag.

### Tag the Dashboard and swap the source to the tagged data model

1. Open the Dashboard for editing, then choose the version to tag:
   1. To tag the latest published version of the document, click the caret () next to the document name and select Tag this published version. If the document is in draft and has unpublished edits, you instead see Tag latest published version.
   2. To tag the latest draft of the document, while editing the document, select the caret () next to the document version and select Tag this version.
   3. To tag a specific version of the document, open the version history of the document by selecting the caret next to the document name > Version history, then locate the version you want to tag. Click  More > Set tag on this version
2. For Choose Tag, choose the tag to apply to the Dashboard version.
3. Select the checkbox for Swap sources of the tagged version.
4. Click Set Tag.
5. In the Modify sources modal, for Sources of tagged Dashboard open the drop-down menu and choose the corresponding tagged version of the data model.
6. Select Swap and tag

### Swap the dataset or connection source used by a tagged Dashboard version

To select a different connection path, database, or schema for a tagged Dashboard version, do the following:

1. Open the Dashboard for editing, then choose the version to tag:
   1. To tag the latest published version of the document, click the caret () next to the document name and select Tag this published version. If the document is in draft and has unpublished edits, you instead see Tag latest published version.
   2. To tag the latest draft of the document, while editing the document, select the caret () next to the document version and select Tag this version.
   3. To tag a specific version of the document, open the version history of the document by selecting the caret next to the document name > Version history, then locate the version you want to tag. Click  More > Set tag on this version.
2. For Choose Tag, choose the tag to apply to the Dashboard version.
3. Check Swap sources of the tagged version and click Set Tag.
4. In the Modify sources modal, click the dropdown under Sources of Tagged Dashboard to change the data source.
5. \[optional] To choose a different database or schema in the selected connection, hover over the database or schema name and select Modify to choose a different database or schema, then select Confirm.
6. Click Swap and tag.\
   The tagged version of the Dashboard is updated to use the new connection. If your Dashboard uses a dataset, a copy of the dataset is created on the new connection.

## Publish changes to a tagged Dashboard version

If you want to make changes to a tagged version of a Dashboard, you must first return the tagged version to a draft state, then make changes and re-tag the version.

For example, if you follow a development lifecycle where you tag a Dashboard version with the "testing" tag before tagging a Dashboard with the "production" tag to indicate that it is ready to use in production, you might want to iterate on the testing tag.

To update the "testing" tagged version of the Dashboard, do the following:

1. Open the Dashboard for editing.
2. Open the version history for the Dashboard.
3. Locate the tagged version and select the date of the associated version to open it.
4. For the version, select  More > Restore version as draft.
5. Make your desired changes in the draft.
6. When you finish making changes, publish your changes.
7. In the Dashboard header menu, open Version history if it is no longer open.\
   In the version history, you see a line item for Restored version from <date>, then additional changes listed above that version.
8. For the current version that contains your changes, select  More > Set tag on this version.\
   The latest version is tagged, and the contents are updated to match.\
   The version that was previously tagged is listed with a grayed-out version of the version tag.
9. If you had other changes that you want to preserve, return to the version before you restored the tagged version as the latest draft, and select  More > Restore version as draft.

### Update a tagged version to use another tag

For example, if you want to promote a tagged Dashboard version from the "staging" version tag to the "production" version tag, do the following:

1. Open the Dashboard for editing.
2. Open the version history for the Dashboard.
3. Locate the tagged version and select the date of the associated version to open the tagged version.
4. In the Dashboard header, select the version menu () and select Move tag to, then select the "Production" tag.
5. In the Set tag on version modal, select any relevant options, then select Set Tag. The "Production" tag is added to the version.
6. Next, remove the "Staging" tag from the version. In the version history, locate the "Staging" tag, then select  More > Remove this tag.
7. In the modal, acknowledge that users granted access only to this tagged version, or embeds that use the link to the tagged version, lose access to the tagged version after removing the tag by selecting Remove.\
   The version appears with a current tag of "Production" and a previous tag of "Staging".

## Share tagged versions of a Dashboard or data model

To control what users and teams can see in a given Dashboard, or what version of a data model users can access, share a tagged version with a user or a team.

When you share a document with access only to a specific version tag, you effectively revoke access to the published version of the document and limit access only to the shared tagged versions. You can use tagged versions like a published version of a document for a given user or team.

For example, you can make a version of a Sales Dashboard that is filtered entirely on the East region, tag that version with East, then share that tagged version with the Sales - East team. They then have view (and explore) access to that version of the Dashboard, but cannot make any changes to the source Dashboard.

To share a tagged version of a Dashboard or data model, do the following:

1. Open the document.
2. In the document header, click Share (icon).
3. In the Share modal, search or browse to find the team or user with whom you want to share the tagged version of the document.
4. Click the Permission drop-down menu, then hover over a permission to select a tag on the Dashboard to which to grant access. Select All (default) to share all versions of the Dashboard with the user or team.
5. Click Share.

If you remove a tag from a document version, users and teams with access only to that tagged version of the document lose access to the document.

### Restrict access to a folder using a version tag

If you use version tagging to manage access to documents, you can set up a workspace or folder to manage access more easily.

You can share a workspace or folder with a user or teams, and grant those users or teams access to a specific tag. If you do so, Dashboards or data models in that workspace or folder must have that tag applied to be accessible to those users or teams.

For example, if you have a sales organization that covers 5 regions, you can create a workspace for each region and grant each sales team Explore access to their workspace with a tag for their region:

If you do so, all Dashboards in the workspace must have a version tagged accordingly. In this example, all Dashboards in the Sales US-East workspace must have a version tagged East so that the members of the Sales US-East team can view and explore the East versions of the Dashboards.

If you grant elevated permissions on the workspace to the team members, such as Can contribute or Can manage, those team members can access all versions of documents in the workspace.

Permissions set at the workspace and folder level are inherited by the Dashboards and documents in the workspace or folder.

## Link to a tagged version of a Dashboard

If you want to link directly to a tagged version of a Dashboard, for example to embed the tagged version of the Dashboard, reference the tag name in the URL.

For example, if you add a staging tag to a Dashboard, the URL for the Dashboard version tagged with staging contains the following:\
`/Dashboard/My-Dashboard-{Dashboard_id}/tag/staging`

The same construct applies for embeds. The staging tag is appended to the URL:\
`/embed/{embed_id}/tag/staging`

Like other URL parameters, version tag names with a space or special characters are encoded. For example, `staging%20copy` for a version tag named "Staging Copy".

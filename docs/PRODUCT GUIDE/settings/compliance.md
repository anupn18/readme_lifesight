---
title: Compliance
excerpt: >-
  New Delete/Export feature provides GDPR compliance for users to manage
  personal data, while store owners can store information securely.
deprecated: true
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Lifesight users can now ensure GDPR compliance by managing personal data through the Delete or Export feature. This feature allows you to manage historical profiles and event-related data efficiently. By leveraging this functionality, Lifesight users can safeguard personal data and ensure GDPR compliance.

<Image align="center" src="https://files.readme.io/d13db45a4de0f74f184d8e6a31e461d67a7298d5a07a6ad855f86cadb46856d8-com.jpg" />

### What is GDPR compliance?

GDPR compliance means adhering to EU rules for processing, storing, and handling personal data. It includes obtaining consent, transparency, and data protection measures.

<br />

### The GDPR focuses on three essential areas for protecting your personal data:

* To comply with GDPR, you must obtain consent from users for marketing campaigns.
* It is essential to protect personal data adequately to ensure compliance.
* If requested, you must promptly delete, correct, or restrict personal data.

***

<br />

## Easy Export Function

As the administrator of the workspace/store, you should be able to export and obtain a JSON file containing all stored contact profiles and event information. The export functionality is only enabled for contacts (Profiles who either have an email, a phone number, or both).

**If you're using a "Lifesight" workspace, you may need to export data for a particular profile. Here's how you can do it:**

1. Log in to your "Lifesight" account.
2. Navigate to the Connect > Profiles feature.
3. Visit the "Profile insights" page for the specific profile that you want to download details for.
4. Click on the "three dots" located in the top right corner of the page and select the "Export" option. Please note that only the workspace admin can access this option.
5. After clicking the "Export" button, you will receive a toast notification indicating the next steps to follow.
6. The status of the request and the file to download can be viewed in "Settings → Compliance → Downloaded".
7. The table displayed shows the name, email, phone number, date, and status of the request.
8. The status can be one of the following values: Pending, Expired, Downloaded, or Download Button.
9. Clicking the "Download" button will download a JSON file containing all the data associated with the profile, including the profile attributes, contact details, and event data such as placed orders and viewed products.
10. The expiry time for the file is seven days from the time of submitting the request. After that, the file will be deleted and the status will be marked as "Expired".

If the store owner requests to export data for the same profile while the previous request is still active and the file has not been downloaded yet, an error message indicating "Already requested for this customer..." will pop up. In that case, the user should go to "Settings → Compliance → Downloaded" and download the file for the corresponding contact.

<br />

## Easy Delete Function

**Here's how you can delete data for a particular profile:**

1. Log in to your Lifesight account to access the platform.
2. Navigate to the profile section.
3. Navigate to the insights page for the contact that you want to delete.
4. Click on the "three dots" in the right top side and click on the "Delete" option - Please note that this is only possible if you are the admin of the workspace.
5. A warning message will appear to confirm your decision.
6. Once you have confirmed the warning message, a toast notification will be displayed to highlight the next steps.
7. You can check the status of the deletion request by going to "Settings → Compliance → Deleted".
8. A table with the fields "Name, Email, Phone Number, Date, Requested By" will be shown. This table provides a permanent record that your business has complied with any deletion requests.
9. When you delete a contact in Lifesight, the profile's event history and all associated recipient records remain in Lifesight, but any sensitive data associated with the profile is removed.
10. The customer's information is permanently deleted from Lifesight for a profile's event history. For every recipient record associated with a profile, the profile's email address is replaced with a random email address that starts with the word "redacted," and if the contact has a phone number, it is replaced with a random alphanumeric string (e.g., 121dc).
11. All the various personally identifiable information (PII) fields associated with the contact will be deleted from the storage.

<br />

## For any future events associated with a deleted profile, the following actions will be taken:

If the contact engages with your site in any way after being deleted (e.g., ordering a product on Shopify, viewing a product, adding to cart, signing up via a signup form, etc.), a new profile will be created for them, and these events can be seen in the profile insights tab under a new profile ID.
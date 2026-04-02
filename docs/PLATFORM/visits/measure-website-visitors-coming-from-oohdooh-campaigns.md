---
title: Measure website visitors coming from OOH/DOOH campaigns
deprecated: false
hidden: false
metadata:
  robots: index
---
Creating a Campaign Measurement  

Once you navigate to 'Visits Module' From the main menu on the left,  Click on the 'Create Measurement' button displayed on the right top corner of the visits module.

![](https://files.readme.io/e579149229dd302b07715224281e089d2eb97c8f33a9b6b3015d3068b0c70d64-image.png)

<br />

You can measure website visitors coming from your OOH/DOOH campaigns.
​
In order to start measuring your OOH/DOOH to website visitors, you will require the following information to complete this process.

![](https://files.readme.io/1b86e849b66011ea3566f4e22f1ac6d2a321012961225d252b4831c3ee9b8336-image.png)

<br />

Flight – How long you will be running your campaign. You may also specify your preferred attribution window

Partners – Which Delivery Partners you will be running your campaigns on.

Budgets – How much you are spending on each Partners

Domain - Domain for which you will measure visitors

The Ad Measurement wizard involves 4 Steps.

​Step 1 - Campaign Name and Flight

Please complete the following:

Campaign Name: Enter a meaningful name to represent your campaign (i.e. Summer Campaign, New Year Promo, Holiday Campaign, etc.)
​

Campaign Flight: You can set campaign flight dates by selecting the campaign start and end dates accordingly.
​

Attribution Flight: Set the attribution start and end date if you want to manually set the attribution window. If you don’t wish to set the attribution date manually, the system will automatically set the attribution window.
​

Override Checkbox: If you need to override the default attribution period, you can check the Override checkbox to set your own attribution start and end date.

If the selected campaign measurement type is OOH
Step 2(a) - Select OOH Media Partner, Partner Budget & Screens
​  

![](https://files.readme.io/2b016d1967807863f9db890b9a1ec2c593f744b08900fa712db7fc7cda98a2e6-image.png)

1. Select Media Partners : Choose Out of Home as a Media partner if you are measuring website visits from Static OOH billboards.

Note - All billboards should be onboarded prior to the campaign measurement creation with the help of your Account Manager
​

2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).
   ​
   3. Select screen: During the creation of measurements for Out-of-Home (OOH) advertising, select or add all the screens that need to be measured.


​Partner Impressions: Based on the booked OOH activity please add estimated impressions/contacts as per the media plan. For OOH impressions means estimated contacts with OOH campaign billboards.

If the selected campaign measurement type is DOOH
Step 2(b) - Select DOOH Media Partner, Partner Budget & Impressions

![](https://files.readme.io/bdf867f6cb8fd84b447023d48af774294feb68299d12aacabce0169680b6618a-image.png)

<br />

1. Select Media Partners : Choose DOOH as a Media Partner if you are measuring website visits from DOOH or pDOOH campaigns.
2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).
3. Partner Impressions: Based on the booked DOOH activity please add estimated impressions/contacts as per the media plan. For DOOH impressions means estimated contacts with DOOH campaign billboards.​

In case of DOOH attribution, choose the on-boarded DOOH Ad log file added as a Data Source from the drop down to map the DOOH Attribution tracker to given DOOH billboards from the ad log files.

To know more about Ad logs on-boarding, please contact your account manager

​Step 3 - Domain name

![](https://files.readme.io/f4000f3f955a917871599208c6ff02089f720d7d35ade8bb221ffed880ebc149-image.png)

Enter the domain name for which you need to measure the website visits

For example - [https://lifesight.io/](https://lifesight.io/)

Once domain is added, hit ‘SAVE'.

Step 4 - Deploying the JavaScript SDK on your website
Embed the following script into your Website header/footer or enable

<script src="https://storage.googleapis.com/measure-insight/measureinsight.min.js" />

**Recommendation - We recommend that you deploy the SDK in a way to ensure that we are able to capture visits to all pages on the website**

​**Tag Deployment via GTM for a 3rd Party Tracker like Lifesight's Web Pixel:**  

​**3rd party Tag Deployment Process via Google Tag Manager**

Step 1: Click on New Tag

![](https://files.readme.io/56dd353401ac519c5eaafba676b63c73825463b1cc105e2b524117cb1284bb29-image.png)

<br />

Step 2: Enter a tag name and click on the edit button next to tag configuration.

![](https://files.readme.io/0d29d5d20e6d34763a155f17aa484b3bd8260b7670c8faacecd760f988bb6721-image.png)

<br />

Step 3: Select Custom HTML Tag - This is to deploy the tag as a 3rd Party function loader

![](https://files.readme.io/c70c6c7c9ffe5d7cb472e59b895f9fda9d07c5a20a9eb340a516ae53315c0a4c-image.png)

<br />

Step 4: Deploy the following tag here.

<script src="https://storage.googleapis.com/measure-insight/measureinsight.min.js" />

![](https://files.readme.io/8e344905b17ec2da3cfcb38b99c60b263b59be608f66993681e14b9e5abeb8de-image.png)

<br />

Step 5: Selecting All Pages as the triggering option


​

![](https://files.readme.io/b54a2b0b89ba2d00ceb8c6bb59beffdf6c78a713b67a0f7ca41b466e0befc493-image.png)

![](https://files.readme.io/82f0455900775b4455ce5c074a9c0e5aa0537aa827f277a6e063449e100af1eb-image.png)

Your tag will look like this after deploying the LifeSight Javascript SDK

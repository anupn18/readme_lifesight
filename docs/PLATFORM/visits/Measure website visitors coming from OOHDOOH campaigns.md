---
title: "Measure website visitors coming from OOH/DOOH campaigns"
intercom_article_id: "10511509"
---

**Creating a Campaign Measurement**

Click on the Measurements icon displayed on the left side of the main menu.

![](../images/e344b727f1a463528e04a329aa0b316e.png)

**You can measure website visitors coming from your OOH/DOOH campaigns.**  
  
In order to start measuring your OOH/DOOH to website visitors, you will require the following information to complete this process.

* Flight – How long you will be running your campaign. You may also specify your preferred attribution window
* Partners – Which Delivery Partners you will be running your campaigns on.
* Budgets – How much you are spending on each Partners
* Domain - Domain for which you will measure visitors

The Ad Measurement wizard involves 4 Steps.

### ​Step 1 - Campaign Name and Flight

![](../images/54bf69f390ba11617ae01ee5c0a688e3.png)

Please complete the following:

1. Campaign Name: Enter a meaningful name to represent your campaign (i.e. Summer Campaign, New Year Promo, Holiday Campaign, etc.)  
   ​
2. Campaign Flight: You can set campaign flight dates by selecting the campaign start and end dates accordingly.  
   ​
3. Attribution Flight: Set the attribution start and end date if you want to manually set the attribution window. If you don’t wish to set the attribution date manually, the system will automatically set the attribution window.  
   ​

Override Checkbox: If you need to override the default attribution period, you can check the Override checkbox to set your own attribution start and end date.

## If the selected campaign measurement type is OOH

### Step 2(a) - Select OOH Media Partner, Partner Budget & Screens ​

![](../images/cf66a6d749d3eb22db1e83169d28edda.png)

1. Select Media Partners : Choose Out of Home as a Media partner if you are measuring website visits from Static OOH billboards.

**Note - All billboards should be onboarded prior to the campaign measurement creation with the help of your Account Manager**  
​  
2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).  
​  
3. Select screen: During the creation of measurements for Out-of-Home (OOH) advertising, select or add all the screens that need to be measured.  
​  
​

![](../images/5ae118bec15aacaeb9cba49744aabe8e.png)

​  
​Partner Impressions: Based on the booked OOH activity please add estimated impressions/contacts as per the media plan. For OOH impressions means estimated contacts with OOH campaign billboards.

## If the selected campaign measurement type is DOOH

### Step 2(b) - Select DOOH Media Partner, Partner Budget & Impressions

![](../images/fc8fda75ffeebae76de913070470af61.png)

1. Select Media Partners : Choose DOOH as a Media Partner if you are measuring website visits from DOOH or pDOOH campaigns.  
​  
2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).  
 ​  
Partner Impressions: Based on the booked DOOH activity please add estimated impressions/contacts as per the media plan. For DOOH impressions means estimated contacts with DOOH campaign billboards.  
​

In case of DOOH attribution, choose the on-boarded DOOH Ad log file added as a Data Source from the drop down to map the DOOH Attribution tracker to given DOOH billboards from the ad log files.  
​

To know more about Ad logs on-boarding, refer to this section in the Integrations module :  
​

​  
​[http://support.lifesight.io/en/articles/5601559-dooh-ad-log-onboarding](https://support.lifesight.io/en/articles/5601559-dooh-ad-log-onboarding)

​

### ​Step 3 - Domain name

![](../images/e344b727f1a463528e04a329aa0b316e.png)

Enter the domain name for which you need to measure the website visits

For example - <https://lifesight.io/>

Once domain is added, hit ‘Add Measurement’.

### Step 4 - Deploying the JavaScript SDK on your website

Embed the following script into your Website header/footer or enable

```
<script src="https://storage.googleapis.com/measure-insight/measureinsight.min.js"></script>
```

**Recommendation - We recommend that you deploy the SDK in a way to ensure that we are able to capture visits to all pages on the website**

​**Tag Deployment via GTM for a 3rd Party Tracker like Lifesight's Web Pixel:**   
​  
​**3rd party Tag Deployment Process via Google Tag Manager**

**Step 1:** Click on New Tag

![](../images/de09248378c6159f903667ef456a9a36.png)

**Step 2:** Enter a tag name and click on the edit button next to tag configuration.

![](../images/c6c7428a44e465c0636e4f4213a635fa.png)

**Step 3:** Select Custom HTML Tag - This is to deploy the tag as a 3rd Party function loader

![](../images/03ea522cc16899ce81a11995b357a590.png)

**Step 4:** Deploy the following tag here.

```
<script src="https://storage.googleapis.com/measure-insight/measureinsight.min.js"></script>
```

![](../images/28d6e6e456ba512ed7d27e3a344d1972.png)

**Step 5:** Selecting **All Pages** as the triggering option  
​

![](../images/cc66aaf9455c3cc63e0ab1085de3df21.png)

Your tag will look like this after deploying the LifeSight Javascript SDK

![](../images/e344b727f1a463528e04a329aa0b316e.png)
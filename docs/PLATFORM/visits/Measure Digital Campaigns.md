---
title: "Measure Digital Campaigns"
intercom_article_id: "9025854"
---

**Creating a Measurement Tracker**

Our Measurement module works using a pixel based implementation in your respective DSP or ad network. To begin, you will need to complete the “Add Measurement” process that will then generate the pixel (tag) to be implemented. This will allow the tool to generate reports that you can use to attribute your campaigns to offline store visits as well as optimize your campaigns.

Click on the Measurements icon displayed on the left side of the main menu.

![](../images/d0a9343bc46a9384a7d874a6c93ce78f.png)

1. You can measure visitors to brand stores through digital campaigns.
2. You can measure visitors to brand stores from your OOH/DOOH campaigns.  
   ​

The Add Measurement wizard involves 4 Steps. You will need to enter several pieces of information to complete this process. Please prepare the information before you begin so you can easily generate the pixel and implement them.

You will require the following information:

* Flight – How long you will be running your campaign. You may also specify your preferred attribution window
* Partners – Which Delivery Partners you will be running your campaigns on.
* Budgets – How much you are spending on each Partners
* Places – Where you want to attribute your campaigns to.
* Competitors - You can add max 3 brands as competition.

## ​Step 1 - Campaign name and Flight

![](../images/54bf69f390ba11617ae01ee5c0a688e3.png)

In Step 1, please complete the following:

1. Campaign Name: Enter a meaningful name to represent your campaign (i.e. Summer Campaign, New Year Promo, Holiday Campaign, etc.)  
   ​
2. Campaign Flight: You can set campaign flight dates by selecting the campaign start and end dates accordingly.  
   ​
3. Attribution Flight: Set the attribution start and end date if you want to manually set the attribution window. If you don’t wish to set the attribution date manually, the system will automatically set the attribution window.  
   ​
4. Override Checkbox: If you need to override the default attribution period, you can check the Override checkbox to set your own attribution start and end date.

## Step 2 - Select Media Partner, Partner Budget & Impressions

![](../images/e7d30c67afa91d10a28a7c90290cc09c.png)

1. Select Media Partners : Choose from a list of Media partners that you are running your digital campaign on.  
   ​
2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).  
    ​
3. Partner Impressions: Based on the campaign booked activity please add estimated impressions/contacts as per the media plan.  
    ​

Enable Conversion Data: In case you want to enable the In-flight optimization feature for Facebook, TTD or Google Marketing Platform ( Display and Video 360), you can enable conversion data to send daily footfall data directly to these partner platforms.

## Step 3 - Select Places ​

![](../images/24f2f1e7d2bdf634007af21b91307eb5.png)

1. In Step 3, you have to select the places you want to track for your attribution places (also known as conversion places). This will be the locations you want to attribute your ad views/clicks/engagements to. To add places, you will need to search places either by Brands (i.e. Starbucks, KFC, McDonald's, etc.) OR Categories (i.e. Fast Food, Restaurant, Cinemas, etc) with further filtration available by ‘States’ and ‘Cities’. By default, the search will be limited to the country you operate in.
2. Search Result: After you click Search, a list of locations will be displayed. In the example above, a search for Adidas in the state of Karnataka with city as Bangalore was done and there were 16 places found.
3. Select Places : You can select multiple locations manually by clicking the checkbox from the list of available places. You can also 'Select All' to do so.
4. 'Remove All' can be used to remove specific checked locations using the button above the list.

## Step 4 - Select Competitors

![](../images/29ce6b58fdae9d1d114d866bd553d6af.png)

In Step 4, you can select upto three competitor brands to measure your campaign against. The system will automatically pick up the competitor store closest to your attributed brand store.

​Note: This screen is available for check only if adding of attribution places is done by 'brands' search. This feature is not available if places are added by ‘category’ search. Adding competitors will help you evaluate the performance of your own brand against them. This step is optional and you can simply skip it if you don’t wish to add competitors.

Once competitors are done adding, hit ‘Add Measurement’.

## ​Step 5 – Copy Tracker

The attribution campaign has now been created successfully and this has generated specific pixels (tags) for each of your media partners.

![](../images/6f675c085f201ec92066e32500410c10.png)

In Step 5, select the ‘Media Partner’ that you have selected at time of tracker creation from the dropdown menu. Then select the 'Creative' type.

You can now copy the tracking code and paste in your respective selected media partner interface.

![](../images/d2714106619138d9b4e8480092716162.png)

The trackers will look similar to the above figure.

Please note that trackers are media partner specific with macros embedded in them for value substitution. Macro parameters in trackers will change basis the media partner used.

## **Step 6 - Add landing page to click tracker**

As shown below, replace the part after “&redirect=” from the click tracker with an encoded landing page URL.

Example:

Click tracker before adding the landing page

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}&redirect=[urlencoded\_redirect\_url](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=%5Bcv%5D&cachebuster=%24%7BCACHEBUSTER%7D&cid=%24%7BCAMPAIGN_ID%7D&crid=%24%7BCREATIVE_ID%7D&db_redirect=NO&app=%24%7BSOURCE_URL_ENC%7D&redirect=%5Burlencoded_redirect_url)]

Eg: Landing page is<https://www.google.com/>

You can use an online tool like<https://www.textfixer.com/html/encode-url.php> to encode your landing page(s).

In this example, the landing page after encoding is https%3A%2F%2Fwww.google.com%2F and add the encoded url in the click tracker as below

Click tracker after adding encoded landing page URL:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}&redirect=https%3A%2F%2F](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=%5Bcv%5D&cachebuster=%24%7BCACHEBUSTER%7D&cid=%24%7BCAMPAIGN_ID%7D&crid=%24%7BCREATIVE_ID%7D&db_redirect=NO&app=%24%7BSOURCE_URL_ENC%7D&redirect=https%3A%2F%2F)[www.google.com%2F](http://www.google.com%2F)

Note: Always test, if the click tracker is redirecting to the landing page by firing the tracker in a browser.

## **Step 7 - Assign custom values to impression & click trackers**

Custom values are used within trackers to track impressions, clicks and visits against custom values such as different creative names or sizes, targeting audiences etc.

As shown below in an example, replace the the [cv]part of the macro within a tracker, with custom names (Eg. Creative\_1 ) that you want to track visits for. Please note there should be no space or special characters in the custom values.

Impression tracker:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=%5Bcv%5D&cachebuster=%24%7BCACHEBUSTER%7D&cid=%24%7BCAMPAIGN_ID%7D&crid=%24%7BCREATIVE_ID%7D&db_redirect=NO&app=%24%7BSOURCE_URL_ENC)}

After modification:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=Creative\_1&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=%5Bcv%5D&cachebuster=%24%7BCACHEBUSTER%7D&cid=%24%7BCAMPAIGN_ID%7D&crid=%24%7BCREATIVE_ID%7D&db_redirect=NO&app=%24%7BSOURCE_URL_ENC)}

Similarly you need to add the same custom name in the click tracker as well:

Click tracker:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=Creative\_1&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}&redirect=https%3A%2F%2F](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=Creative_1&cachebuster=%24%7BCACHEBUSTER%7D&cid=%24%7BCAMPAIGN_ID%7D&crid=%24%7BCREATIVE_ID%7D&db_redirect=NO&app=%24%7BSOURCE_URL_ENC%7D&redirect=https%3A%2F%2F)[www.google.com%2F](http://www.google.com%2F)
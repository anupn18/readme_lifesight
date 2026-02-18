---
title: Creating Measurement Trackers
deprecated: false
hidden: true
metadata:
  robots: index
---

Our Measurement module works using a pixel based implementation in your respective DSP or ad network. To begin, you will need to complete the “Add Measurement” process that will then generate the pixel (tag) to be implemented. This will allow the tool to generate reports that you can use to attribute your campaigns to offline store visits as well as optimise your campaigns.

Click on the Measurements icon displayed on the left side of main menu.

You can measure visitors to brand stores through digital campaigns.

You can measure visitors to brand stores from your OOH/DOOH campaigns.
​

The Add Measurement wizard involves 4 Steps. You will need to enter several pieces of information to complete this process. Please prepare the information before you begin so you can easily generate the pixel and implement them.

You will require the following information:

Flight – How long you will be running your campaign. You may also specify your preferred attribution window

Partners – Which Delivery Partners you will be running your campaigns on.

Budgets – How much you are spending on each Partners

Places – Where you want to attribute your campaigns to.

Competitors - You can add max 3 brands as competition.

​Step 1 - CAMPAIGN NAME AND FLIGHT
​

In Step 1, please complete the following:

Campaign Name: Enter a meaningful name to represent your campaign (i.e. Summer Campaign, New Year Promo, Holiday Campaign, etc.)
​

Campaign Flight: You can set campaign flight dates by selecting the campaign start and end dates accordingly.
​

Attribution Flight: Set the attribution start and end date if you want to manually set the attribution window. If you don’t wish to set the attribution date manually, the system will automatically set the attribution window.
​

Override Checkbox: If you need to override the default attribution period, you can check the Override checkbox to set your own attribution start and end date.
​
​Step 2 - SELECT MEDIA PARTNERS,PARTNER BUDGET & IMPRESSIONS

Select Media Partners : Choose from a list of Media partners that you are running your digital campaign on.
​

Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit  (CPV).
​

Partner Impressions: Based on the campaign booked activity please add estimated impressions/contacts as per the media plan.
​

Enable Conversion Data: In case you want to enable the In-flight optimisation feature for Facebook, TTD or Google Marketing Platform ( Display and Video 360), you can enable conversion data to send daily footfall data directly to these partner platforms.
​
​ Step 2 - SELECT OOH/DOOH MEDIA PARTNER,PARTNER BUDGET & IMPRESSIONS
​

1. Select Media Partners : Choose Out of Home as a Media partner if you are measuring footfalls from Static OOH campaigns.
   ​

2. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).
   ​
   ​Partner Impressions: Based on the booked OOH/DOOH activity please add estimated impressions/contacts as per the media plan. For OOH/DOOH impressions means estimated contacts with OOH/DOOH campaign billboards.
   ​

3. Select Media Partners : Choose DOOH as a Media Partner if you are measuring footfalls from DOOH or pDOOH campaigns.
   ​

4. Partner Budget: Mention partner wise planned budget. Mentioning exact budgets would help in determining correct partner wise Cost per Visit (CPV).
   ​

Partner Impressions: Based on the booked OOH/DOOH activity please add estimated impressions/contacts as per the media plan. For OOH/DOOH impressions means estimated contacts with OOH/DOOH campaign billboards.
​

In case of DOOH attribution, choose the on-boarded DOOH Ad log file added as a Data Source from the drop down to map the DOOH Attribution tracker to given DOOH billboards from the ad log files.
To know more about Ad logs on-boarding, refer to this section in the Integrations module :
​
​[http://support.lifesight.io/en/articles/5601559-dooh-ad-log-onboarding](http://support.lifesight.io/en/articles/5601559-dooh-ad-log-onboarding)
​
​
​Step 3 - SELECT PLACES
​

In Step 3, you have to select the places you want to track for your attribution places (also known as conversion places). This will be the locations you want to attribute your ad views/clicks/engagements to. To add places, you will need to search places either by Brands (i.e. Starbucks, KFC, McDonald's, etc.) OR Categories (i.e. Fast Food, Restaurant, Cinemas, etc) with further filtration available by ‘States’ and ‘Cities’. By default, the search will be limited to the country you operate in.

Search Result: After you click Search, a list of locations will be displayed. In the example above, a search for Adidas in the state of Karnataka with city as Bangalore  was done and there were 16 places found.

Select Places : You can select multiple locations manually by clicking the checkbox from the list of available places.  You can also 'Select All' to do so.

'Remove All' can be used to remove specific checked locations using the button above the list.

Step 4 - SELECT COMPETITORS(S)

In Step 4, you can select upto three competitor brands to measure your campaign against. The system will automatically pick up the competitor store closest to your attributed brand store.
​
​Note: This screen is available for check only if adding of attribution places is done by 'brands' search. This feature is not available if places are added by ‘category’ search. Adding competitors will help you evaluate the performance of your own brand against them. This step is optional and you can simply skip it if you don’t wish to add competitors.

Once competitors are done adding, hit ‘Add Measurement’.
​
​STEP 5 – COPY TRACKER

The attribution campaign has now been created successfully and this has generated specific pixels (tags) for each of your media partners.

In Step 5, select the ‘Media Partner’ that you have selected at time of tracker creation from the dropdown menu. Then select the 'Creative' type.

You can now copy the tracking code and paste in your respective selected media partner interface.

The trackers will look similar to the above figure.

Please note that trackers are media partner specific with macros embedded in them for value substitution. Macro parameters in trackers will change basis the media partner used.

Step 6 - Add landing page to click tracker

As shown below, replace the part after “&redirect=” from the click tracker with an encoded landing page URL.

Example

Click tracker before adding the landing page

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=[cv]&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}&redirect=[urlencoded_redirect_url](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK\&channel=gmp\&cv=\[cv]\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC}\&redirect=\[urlencoded_redirect_url)]

Eg. Landing page is [https://www.google.com/](https://www.google.com/)

You can use an online tool like [https://www.textfixer.com/html/encode-url.php](https://www.textfixer.com/html/encode-url.php) to encode your landing page(s).

In this example, the landing page after encoding is https%3A%2F%2Fwww.google.com%2F and add the encoded url in the click tracker as below

Click tracker after adding encoded landing page URL:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=[cv]&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}&redirect=https%3A%2F%2Fwww.google.com%2F](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK\&channel=gmp\&cv=\[cv]\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC}\&redirect=https%3A%2F%2Fwww.google.com%2F)

Note: Always test, if the click tracker is redirecting to the landing page by firing the tracker in a browser.

Step 7 - Assign custom values to impression & click trackers

Custom values are used within trackers to track impressions, clicks and visits against custom values such as different creative names or sizes, targeting audiences etc.

As shown below in an example, replace the the [cv]part of the macro within a tracker, with custom names (eg. Creative_1 ) that you want to track visits for. Please note there should be no space or special characters in the custom values.

Impression tracker:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=[cv]&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER\&channel=gmp\&cv=\[cv]\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC})

After modification:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER&channel=gmp&cv=Creative_1&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=RENDER\&channel=gmp\&cv=Creative_1\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC})

Similarly you need to add the same custom name in the click tracker as well:

Click tracker:

[https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK&channel=gmp&cv=Creative_1&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}&redirect=https%3A%2F%2Fwww.google.com%2F](https://pixel.ad.lifesight.io/pixel/event/D2KJ2M?event=CLICK\&channel=gmp\&cv=Creative_1\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC}\&redirect=https%3A%2F%2Fwww.google.com%2F)

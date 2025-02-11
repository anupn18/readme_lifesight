---
title: How to setup custom attribution weights
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
## Custom Attribution Weights in Lifesight: How They Work and How to Use Them

In this article, we will explain how Lifesight handles custom attribution weights as part of our **Algorithmic Attribution Model**, how you can provide custom weights for your channels, and how these weights are used in the backend to deliver more accurate attribution insights. We will also walk you through the process of ingesting custom weights and what it looks like in the Lifesight platform.

### What Are Custom Attribution Weights?

Custom attribution weights allow you to apply specific weightings to different marketing channels based on either **Lifesight's Data-Driven Attribution (DDA) model** or any other attribution model. In the Lifesight DDA model, weights are automatically calculated based on customer journeys (both converting and non-converting) to assign proper credit to channels involved in a conversion.

However, if you have your own attribution model and prefer to use your own weights, Lifesight enables you to submit these weights, which can then be ingested and applied across your data.

### How Lifesight's Algorithmic Attribution Works

Lifesight’s **Algorithmic Attribution** uses data collected from customer interactions on your website or app. Here's how the process works:

1. **Lifesight SDK Installation**: Once the Lifesight SDK is installed, it starts collecting data from all user interactions (page views, clicks, purchases, etc.). This data is vital for tracking customer journeys.

2. **Customer Journey Tracking**: Lifesight builds a detailed customer journey based on user activity and UTM parameters. 

3. **Attribution Weight Calculation**: For users who don’t provide custom weights, Lifesight uses a Data-Driven Attribution (DDA) model to automatically assign **channel weights** for each journey.

4. **Attribution Insights**: These weights are consumed by Lifesight's backend services, which calculate the attributed revenue and other key metrics based on the contribution of each channel.

### Submitting Custom Attribution Weights

If you have your own custom attribution weights for each channel, you can submit them to Lifesight. Here’s how we process these weights:

1. **Contacting Support**: Reach out to our support team with the weights for your channels. The weights should be in the format of a **normalized attribution credit** for each channel, They should sum upto 1. For example:

   ```
   Channel Name     | Normalized Attribution Credit
   --------------------------------------------------
   Facebook         | 0.3
   Google           | 0.5
   TikTok           | 0.2
   ```

2. **Backend Ingestion**: Once we receive your custom weights, our implementation team will ingest these weights into Lifesight's backend. 

3. **Adjustments for Missing Channels**: If a journey includes channels for which no custom weights are provided (e.g., Axio in the following journey), Lifesight uses a **Multi-Touch Linear Model** to estimate the missing channel’s contribution. For example:

   - **Journey**: `[Facebook] >[Google] >[Facebook] >[TikTok] > [Axio]`
   - **Weights (Provided)**: Facebook - 0.3, Google - 0.5, TikTok - 0.2
   - **Estimation for Axio**: Based on the linear model, Axio's coefficient is normalized to fit within the overall weight distribution, ensuring the sum of all channel weights equals 1.

4. **Final Weights**: Once the coefficients for all channels are normalized, the final readjusted weights for this journey will look like this:

   ```
   Channel    | Final Normalized Weights
   -------------------------------------
   Facebook   | 0.25
   Google     | 0.4167
   TikTok     | 0.1667
   Axio       | 0.1667
   ```

### How Custom Weights Appear in the Platform

After the weights have been uploaded, you can start viewing the custom attribution results in the **Attribution Dashboard** under the **Algorithmic Model**.

#### Step-by-Step Process

1. **Access the Attribution Dashboard**:
   - Navigate to the **Attribution** section in the Lifesight platform.
   - Select the **Algorithmic Attribution** model from the available options.

2. **View Attribution Results**:

   - On the dashboard, you will now see the attribution insights for your channels based on the custom weights provided. 
   - The weights will be reflected in the attribution of revenue, conversions, and other key performance metrics across different channels.

3. **Filter by Custom Weights**:
   - You can filter the results by **Channel**, **Date Range** to see how the custom weights impact your attribution.
   - Lifesight will display the **attributed revenue** and other metrics for each channel based on the custom weights you provided.

### Normalization of Weights

When custom weights are applied, Lifesight ensures that the weights are normalized for each customer journey. Here's a breakdown of how normalization works in Lifesight:

1. **Normalization of Channel Weights**:
   - For each journey, the custom weights are normalized to ensure that the total attribution credit across all channels equals 1.
   - Example: In a journey where the total sum of custom weights is 1.2, Lifesight adjusts the channel weights accordingly, dividing each by 1.2 to make sure the sum equals 1.

2. **Normalization of Objective and Campaign-Level Weights**:
   - Lifesight also calculates objective and campaign-level coefficients by multiplying the custom channel weights with the linear fractions derived from the customer journey.
   - These coefficients are further normalized to ensure the total attribution across objectives or campaigns equals 1.

### Conclusion

Custom attribution weights allow you to personalize how your marketing channels are credited for conversions and other key metrics. By utilizing Lifesight's platform, you can either rely on our Data-Driven Attribution model or upload your own weights for more precise control over attribution. Once your custom weights are ingested and the algorithmic attribution model is enabled, the platform will automatically display results using the custom model, providing you with actionable insights to optimize your campaigns.

If you have any further questions or need assistance with uploading custom weights, don’t hesitate to contact our support team!
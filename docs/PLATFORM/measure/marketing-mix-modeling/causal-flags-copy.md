---
title: Causal flags (COPY)
excerpt: >-
  Understand what different causal flags mean in the MMM Insights Contribution
  table
deprecated: false
hidden: false
metadata:
  robots: index
---
Causal flags in Marketing Mix Modeling (MMM) play a crucial role in determining whether the channels included in the model are causal or not. The identification of causal channels helps in accurately attributing the impact of different marketing activities on business outcomes like revenue, leads, or customer acquisition. This article explains the criteria for evaluating causality in MMM channels and how to handle variables with high interaction effects.

<Image align="center" src="https://files.readme.io/4838795efa963a0039509ccd8628f6116348dc341d31ba526e61d9cf665d76ed-causal_flags.jpg" />

## Understanding Causality in MMM

Causality in an MMM context refers to the model's ability to attribute the effect of a specific marketing channel on a business outcome, like revenue or customer growth. The effectiveness of this attribution depends on the quality and variation of the data provided.

### Lifesight shows 3 types of causal flags in the MMM Insights UI:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Causal Flag
      </th>

      <th>
        Indication
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![](https://files.readme.io/77f9c4b6b38f9d817a81a98d9149c11610de1d0d4524788a7a6007ff69e7c1f9-image.png)
      </td>

      <td>
        Is Causal
      </td>

      <td>
        * *1. Criteria*\* - Channels are considered causal if there is a significant amount of data for each channel and the difference in spends across channels is well-defined. Additionally, the correlation values between channels should be \<0.75.
        * *2. Explanation -*\* When channels have low correlation with each other, the model can effectively distinguish the incremental contribution of each channel to the overall outcome. The MMM model identifies the causality more accurately when there is enough variation in channel spends and the relationships between channels are not too closely aligned.
      </td>
    </tr>

    <tr>
      <td>
        ![](https://files.readme.io/1d843cb341825579ce279b7b906a306da0f77914dc6e06d4a8ed6c6bcf643944-image.png)
      </td>

      <td>
        Not Causal (Experiment Needed)
      </td>

      <td>
        * *Criteria*  - If the correlation between channels is >0.75, it becomes challenging for the model to distinguish each channel's impact. In such cases, an experiment is recommended to calibrate the model. Experiments can provide additional data points to help the model identify the incrementality of one channel over another.
      </td>
    </tr>

    <tr>
      <td>
        ![](https://files.readme.io/02e8fbc74922119fd7a5140eec28818c0f9cdd1f97e79ec0d849f443444f261b-image.png)
      </td>

      <td>
        High Interaction Effect
      </td>

      <td>
        * *1. Explanation*\* - High interaction effects occur when there is a strong correlation between independent variables (e.g., in-app game tokens) and dependent organic variables (e.g., revenue), may cause the model to incorrectly attribute performance. This is especially true when both variables essentially represent the same business outcome.
        * *2. Example*\* - Imagine a gaming company that used both gaming tokens and revenue as input variables in the MMM model. Gaming tokens are purchased by users using real money, meaning both gaming tokens and revenue are related to the revenue KPI. The MMM model mistakenly treated gaming tokens as an organic variable, assuming that tokens were contributing independently to revenue, rather than being a form of revenue itself.

        Solution would be to either mark the variable as an outcome KPI variable; Add the flagged variable as a KPI: This is recommended when both the variable and the KPI measure similar outcomes (like revenue) OR re-running the Model without the flagged variable: If the flagged variable is redundant or incorrectly classified, it should be removed. The model can then be re-run with the updated data set to produce more accurate insights.
      </td>
    </tr>
  </tbody>
</Table>

<br />

Causal flags are essential in assessing the effectiveness of an MMM model. By understanding which channels are causal, which require experiments to establish causality, and how to handle high interaction effects, businesses can significantly improve their model accuracy and marketing optimization efforts.
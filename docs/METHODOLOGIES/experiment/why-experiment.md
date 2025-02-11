---
title: Why Experiment ?
excerpt: Learn how to build a test and learn program within your marketing organization
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: experiment
      title: Experiment
---
Experiments includes a set of tools and techniques to ascertain the true **Incremental Contribution** of media channels / tactics / campaigns. Experiment is also the best approach to establish **Causality**  between media interventions and the outcome that it drives. 

> 📘 Experiment is considered the Gold Standard of Measurement

A simplified description of the approach of Experiment is to look at it as a way to create a **Control** and a **Treatment** group of **Test Units** ( refer to "Level" in the table below to understand what _Test Units_ are) **Intervene** with the treatment group (this intervention happens through spend changes, pricing changes etc...) with some treatments and compare the outcomes between these groups and compute the lift within certain levels of (acceptable) statistical significance.

This is achieved by running "**Randomized**" and "**controlled**" tests (RCT) at various levels.

<br />

## Randomization can happen at 3 levels

[block:parameters]
{
  "data": {
    "h-0": "# ",
    "h-1": "Level",
    "h-2": "Test Type",
    "h-3": "Description",
    "0-0": "1",
    "0-1": "Geography",
    "0-2": "Geo Test",
    "0-3": "Pick a group of market clusters with control and treatment geographies  \nin such a way that they are similar to one another in some aspects.  \nIntervene in the treatment cluster and measure the impact of the  \nintervention over the testing period",
    "1-0": "2",
    "1-1": "Time Period",
    "1-2": "Spend Test",
    "1-3": "Compare two different time periods after adding \"right\" variations into the  \nspend. Compare the outcome across these time periods to understand  \n the impact of the Variations",
    "2-0": "3",
    "2-1": "Segment",
    "2-2": "Split Test",
    "2-3": "Pick a segment of first party profiles, randomly separate them to control and  \ntreatment groups with right sizes. Expose the treatment group with  \nad campaigns that needs testing. Compare the outcome from control  \nand treatment groups over the test period and compute the lift"
  },
  "cols": 4,
  "rows": 3,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

Though experiments are considered the best approach to measuring incrementality, adopting experiments at scale in marketing context poses some practical (& statistical) challenges.

## These are the 3 biggest challenges in running a good experiment

1. **Randomisation**  
   True randomisation is hard to achieve in marketing - whether that be for different groups of profiles, geographies or periods in time. We need to adopt advanced algorithms for customer segmentation and lookalike, market matching & smart spend levels and period selection
2. **Control**  
   Marketing environment is influenced by a number of variables. Every user is exposed to the "Brand" continuously through different media and channels. When a test is underway, we need to control for two things 
   1. Control group is kept away from any influence of the intervention
   2. The impact of all the "other" variables should be kept constant or with limited variations during the flight of experiment  
      Refer the diagrams below to understand more about the "Control Problem"
3. **Ad Stock Creep**  
   The period before and after the Test Period continue to influence and potentially corrupt the test period. The ad stock of the pre-test period will creep into your testing window. Should we add a "cooling period" between pre-test period and test period. What should be the ideal gap of this cooling period and what's the best way to control for this period.  
   At what point will we stop testing and adopt the result. The intervention on the test period will continue to create impact even after we close the testing window. How can we adjust for this ad stock effect ? 

<br />

## Example of a Test Setup

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c05f53d-H2_-_2024.jpg",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


What we see above is an (over)simplified view into Experiments. A more realistic view of all the complexity will look like this 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c71bbf0-2.jpg",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Because of the challenges posed by Randomization, Control & Ad Stock Creep, marketing experiments are different from the traditional experiments run in laboratory settings. While we compute the impact of the interventions over control and test group, we also need to account for the confounders, approximate for ad stock and saturation of channels and also model for other variations to get accurate test reads. 

Keeping all of this in perspective, marketing experiments, in reality, are at best quasi-causal in nature.  
There are multiple approaches to quantify for causal impact between treatment and control groups. Some of the popular ones are : Difference in Difference, Synthetic Control Method, Regression Discontinuity and Ridge Regression.

Experiment methodology used by Lifesight is detailed in [Experiments Methodologies](https://docs.lifesight.io/docs/incrementality-testing)
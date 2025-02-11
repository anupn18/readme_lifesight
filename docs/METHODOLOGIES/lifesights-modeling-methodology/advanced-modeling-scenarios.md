---
title: Advanced Modeling Scenarios
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
**Granular Models**  
Granular models are created for the purpose of generating granular MMM insights - at campaign or sub campaign levels. Example : Incrementality at specific TV Channels / Shows Level.  Incrementality at various KOL Influencer level, etc... 

- Granular models need to be run separately from the main model.
- Decomposed KPI data of the main model is passed into another model, along with the sub-component/factors of the independent variable to model for granular insights
- Purpose of having a granular models is to get granular insights only (i.e, when [ifactor](https://docs.lifesight.io/docs/causal-attribution#methodology-of-causal-attribution) application is not possible for attribution calibration)
- We do not roll up granular models to master models (i.e, additive modeling is not supported for this)

**Hierarchical Models**

- A brand might want to run models across multiple geos / product levels
- Lifesight support hierarchical modeling across one dimension
- Our approach is to run separate models across the dimension and then aggregate the models to create one master model.
- Users can use the models separately for planning and optimisation for a geo/product, Or
- Users can use the national/brand level model (i.e, the master model) for overall optimisation

**Nested Models**

- Lifesight today run nested models based on one assumption - i.e BOF investment is not truly independent of TOF investments. (i.e, independence assumption of input variables are violated from regression in this context)
- Nested models are created to capture interaction effect between input variables
- If users want to capture any other interactions (other than TOF influencing BOF), they can let our marketing scientist know about this and we shall incorporate that into the model
- We will very soon make these assumptions of interactions transparent in the UI and we will let users update these "relationships" while building the model itself

**Additive  Models**

- This is the option to merge multiple models into one
- In Lifesight this is not an automated process yet (as model merge needs a lot of data validation on the existing models)
- Example : We currently run separate models for Shopify , Offline , Marketplace revenue. If the user wants to make decisions at overall revenue level, we need to merge these separate models to one unified model.
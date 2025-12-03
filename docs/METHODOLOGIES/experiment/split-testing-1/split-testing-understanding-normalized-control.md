---
title: 'Split Testing : Understanding normalized Control'
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
Imagine you’re running an experiment where you want to see if a campaign made people spend more money. You split your audience into two groups: a **treatment group** (the ones who saw the campaign) and a **control group** (the ones who didn’t). But sometimes these groups aren’t the same size, so we need to make a fair comparison by adjusting the numbers.

## Example

Imagine you have:

* **60 users** in the treatment group (saw the campaign).
* **40 users** in the control group (did not see the campaign).
* Each user spends **$10**.

At first glance, you might think the treatment group outperformed the control group because:

* Total spend in treatment group = `60 users * $10 = $600`
* Total spend in control group = `40 users * $10 = $600`

However, these groups are not the same size, so we need to **normalize** for a fair comparison.

```
Treatment group total spend: $600  
Control group total spend: $400  
Treatment group size: 60  
Control group size: 40  
Normalized control  = ($800 / 40) \* 60 = $1200


Lift = Treatment group total spend - Normalized control = $1000 - $1200 = -$200



```

In this case, the **negative lift indicates** that the treatment group actually performed worse than expected based on the control group's performance.

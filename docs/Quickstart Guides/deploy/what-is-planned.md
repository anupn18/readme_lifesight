---
title: What is planned(Coming soon)
excerpt: Work that is specified but not yet shipped in Deploy.
deprecated: false
hidden: false
metadata:
  robots: index
---
Deploy today helps you manage budget and bid changes at campaign and ad set level, and more is on the way. This page lists what is specified but not yet in the product, so you can tell the difference between a gap and a bug. Nothing here carries a date. Treat it as intent, not commitment.

## Bid target recommendations

You can view and change bid targets today, but Lifesight does not recommend them yet. If you open the bid dialog in Recommended mode, every entity (a campaign or an ad set) shows "no recommendation". This is expected, because no recommended bid value is produced yet.

**Planned:** a recommended bid target alongside the recommended budget, offered through the same Recommended and Custom choice.

## Warnings before you apply

Warnings are designed but not yet live. Today, the apply dialogs always show no warnings on the selected entities.

**Planned:** two kinds of warning. Neither will block a change.

**Caution** flags a change worth a second look:

* A change that is large compared to the current budget
* An increase that runs well ahead of recent delivery
* An entity that shares a budget pool with others that would move with it

**Informational** flags useful context:

* A campaign near its end date
* A lifetime budget with little runway left
* An entity too new for its delivery to have settled

## Guardrails you can set

No setting is configurable today. Recommendations run on system defaults, and there is nothing in the product to change them.

**Planned:** four settings, each applied across the workspace. Once configured, every plan in that workspace follows the same guardrails.

* **Allocation weight:** how much emphasis goes on spend share versus conversion share. Spend share favors campaigns with larger budgets. Conversion share favors campaigns delivering more results. This setting decides whether recommendations lean toward scaling high-spend campaigns or high-performing ones.
* **Cap percentage:** a ceiling on weekly budget increases. With a 20% cap, no campaign's budget grows more than 20% in a week, even if the recommendation is higher. This keeps changes manageable and avoids pushing campaigns out of their learning phase (the period when an ad platform is still optimizing delivery).
* **Minimum days remaining:** the fewest days a campaign must have left in its schedule to get a recommendation. A campaign about to end is a poor candidate for scaling.
* **Lifetime spending threshold:** campaigns close to using up their lifetime budgets are deprioritized automatically, so they don't get increases they can't spend.

## Matching counts across Causal Attribution and Deploy

Today, Causal Attribution generates recommendations for every entity mapped to a tactic (the role a group of campaigns plays, such as prospecting or retargeting). Deploy then filters these down to what it can action. This means the two can show different counts.

**Planned:** eligibility checked once, when recommendations are generated. Anything Deploy shows will already be deployable, and the two counts will always match.

## Recommendations that stay visible

Today, Deploy shows a status against each row.

**Planned:** remove the status column. A recommendation will stay visible as long as the entity remains eligible, and deployment history will live in Logs only. A budget is something you keep managing, not a task you complete once.

## Tactic column

The Tactic column exists but is not filled in yet.

**Planned:** populate it from your taxonomy mapping.

## More tabs in Deploy

**Planned:** Geo Targeting and Creative tabs alongside Budget & Bid.

* **Geo Targeting** will cover market-level changes, including applying and removing the exclusions a geo holdout experiment needs.
* **Creative** will bring the Scale, Refresh, Maintain and Pause actions from the Creative module into the same apply and logging flow.

## Frequently Asked Questions

**Is something missing in Deploy a bug or a planned feature?**

Check this page first. If the feature is listed here, it is planned but not yet in the product. If it is not listed and something isn't working as described in the Deploy docs, contact support.

**When will these features be available?**

Nothing on this page carries a date. Treat it as intent, not commitment.

**Why does the bid dialog show "no recommendation"?**

Bid target recommendations are not live yet. You can still view and set bid targets yourself using Custom.

**Why do I never see warnings when I apply a change?**

Warnings are designed but not yet live. Today, the apply dialogs always show no warnings.

**Will warnings stop me from applying a change?**

No. Both Caution and Informational warnings are meant to inform you, not block you.

**Can I change how recommendations are calculated?**

Not yet. Recommendations run on system defaults today. Allocation weight, cap percentage, minimum days remaining and lifetime spending threshold are all planned as workspace settings.

**Will the planned settings apply per plan or per workspace?**

Per workspace. Once configured, every plan in that workspace follows the same guardrails.

**Why do Causal Attribution and Deploy show different recommendation counts?**

Causal Attribution generates recommendations for every entity mapped to a tactic. Deploy only shows the ones it can action. A planned change will make the two counts match.

**Why is the Tactic column empty?**

It is not populated yet. It will be filled from your taxonomy mapping.

**Will the status column go away?**

Yes, that is planned. Recommendations will stay visible while the entity is eligible, and deployment history will live in Logs.

**Can I manage geo or creative changes in Deploy?**

Not yet. Geo Targeting and Creative tabs are planned alongside Budget & Bid.

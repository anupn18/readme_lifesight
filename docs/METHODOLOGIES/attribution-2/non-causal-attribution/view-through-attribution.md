---
title: View-Through Modeling
excerpt: >-
  How Lifesight credits ads that were seen but not clicked: it models which
  visitors each channel likely reached, then reports click-through and
  view-through credit side by side.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Plenty of ads do their job without a click. Someone watches your video ad on Instagram, and that evening types in your URL or searches for your brand. Analytics records that visit as direct or organic, so the channel that created the demand gets no credit for it.

View-through modeling recovers that influence. Your ad platforms report how many impressions each channel delivered each day, but not who saw them. Lifesight models which of your visitors each channel most likely reached, adds those modeled impressions to the visitors' journeys, and lets your attribution models credit them alongside clicks.

In short:

* Each day, Lifesight models which visitors each channel reached, from three signals: the impressions each channel delivered, each visitor's channel history, and a protected share of genuinely direct traffic.
* Every conversion is credited twice: once as click-through (tracked clicks only) and once as view-through (tracked clicks plus modeled impressions). The **Attribution Method** setting on your attribution dashboards switches between the two.
* Each conversion's credit adds up to 100% in both views. View-through changes which touchpoints get the credit; it never adds conversions or revenue.

## Why view-through has to be modeled

The ad platforms you connect report impressions to Lifesight as totals per channel, campaign and day. None of them says which people saw an ad, so exposure has to be estimated.

What Lifesight does see is your own website traffic. The Lifesight SDK records each visit and where it came from: an ad click, an organic search or referral, or a direct visit. View-through modeling combines this first-party history with each channel's delivered impressions to estimate who was exposed.

The model rests on five assumptions:

1. The effect of an ad that's seen but not clicked shows up later as a direct visit, a branded search or an organic search.
2. A visitor who has come to your site from a channel before is more likely to be reached by that channel's ads again.
3. On any given day, a channel's reach is in proportion to the impressions it delivered.
4. Not all direct traffic is driven by ads. Part of it is a genuinely direct baseline.
5. The lag between seeing an ad and visiting your site is under a day.

## Two views of every conversion

For every conversion, Lifesight calculates two sets of credit at the same time:

| View | Touchpoints that can earn credit |
| :--- | :--- |
| **Click-through** | Tracked clicks only: ad clicks and other visits from a known source, such as an organic search or a referral. Direct gets the credit only when there's no click in the attribution window. |
| **View-through** | The same tracked clicks, plus modeled impressions. Direct gets the credit only when there's neither. |

Both views are calculated for the Last Touch, First Touch, Multi-Touch (Linear) and Algorithmic models, for every attribution window, and for every conversion type: purchases, checkouts, sign-ups, add-to-carts and form submissions. Switching the **Attribution Method** setting doesn't recalculate or overwrite anything. You're choosing which of two stored results to look at, so the comparison is always like for like.

## What the model uses

**Delivered impressions.** Every day, Lifesight reads the impressions each channel delivered from your connected ad accounts, such as Meta, Google Ads, DV360, TikTok, LinkedIn, Snapchat, X, Pinterest, Microsoft and Criteo. Only channels that delivered impressions on a given day take part in that day's model, and a channel that delivered 600,000 impressions gets a larger share than one that delivered 100,000.

**Channel affinity.** From each visitor's full visit history, Lifesight works out which channels they've come from, and in what proportion. A visitor whose visits came from Meta, then Google, then Meta has an affinity of 0.67 for Meta and 0.33 for Google. Visits are matched to channels by their ad click IDs and UTM tags.

**Direct factor.** Lifesight divides the day's direct visits by the total clicks your ad platforms reported for that day. The higher the factor, the more of that day's traffic is treated as genuinely direct. Lifesight doesn't model a day when there were no direct visits, no reported clicks, or at least as many direct visits as reported clicks: on those days, the comparison can't separate ad-driven traffic from the baseline.

## How impressions are modeled each day

Once a day, Lifesight models impressions for the most recent completed day:

1. **Collect delivered impressions.** Lifesight totals the impressions each channel delivered that day.
2. **Calculate the direct factor.** The day's direct visits ÷ the clicks your ad platforms reported. Days with no direct visits, no reported clicks, or a factor of 1 or more are skipped.
3. **Give each channel a share.** A channel's share is its share of the day's impressions × (1 − direct factor). Together, the channels' shares come to (1 − direct factor) of the pool; what's left is the direct baseline.
4. **Build the pool.** The pool is everyone who visited your site that day at least once directly, from an organic search or referral, or through a link carrying a search keyword (a `utm_term` value), such as a branded search.
5. **Look up channel affinity** for everyone in the pool.
6. **Match visitors to channels.** Lifesight goes through the day's channels from the largest share to the smallest. Each visitor with affinity for a channel is matched to it, unless they've already been matched to a larger channel. If those visitors don't fill the channel's share, Lifesight tops it up with other visitors from the pool.
7. **Record the impressions.** Each matched visitor gets one modeled impression from their channel, timestamped to the start of that day. Visitors who weren't matched get no channel impression and stay direct. Once a day's impressions are recorded, they're kept as they are: later runs don't regenerate them.

### Worked example

Say that on a Tuesday your ad accounts report the impressions below and 20,000 clicks, and your site gets 4,000 direct visits. The direct factor is 4,000 ÷ 20,000 = 0.2, so the channels' shares come to 80% of the pool and the direct baseline is 20%.

| Channel | Impressions delivered | Share of impressions | Share of the pool |
| :--- | ---: | ---: | ---: |
| Meta | 600,000 | 60% | 48% |
| Google Ads | 300,000 | 30% | 24% |
| TikTok | 100,000 | 10% | 8% |
| Direct baseline |  |  | 20% |

With 1,000 visitors in Tuesday's pool, Meta's share is 480 visitors, Google's is 240 and TikTok's is 80. Meta is matched first: every visitor in the pool with Meta affinity gets a modeled Meta impression, and if that's fewer than 480 visitors, Lifesight adds other visitors from the pool until Meta reaches 480. Google and then TikTok follow in turn, from the visitors who are left. Anyone still unmatched stays direct.

Shares decide how many visitors are added beyond those with affinity. Visitors with affinity for one of the day's channels are matched whatever the shares, so on a day when most of the pool has channel history, more than 800 visitors can be matched and the direct baseline ends up below 200.

## How modeled impressions earn credit

In the view-through view, a modeled impression is treated like a tracked click under each of these models. In the table below, a click means any tracked visit from a known source, and only touchpoints inside the attribution window count.

| Attribution model | Click-through | View-through |
| :--- | :--- | :--- |
| **Last Touch** | The last click gets 100%. | The later of the last click and the last modeled impression gets 100%. |
| **First Touch** | The first click gets 100%. | The earlier of the first click and the first modeled impression gets 100%. |
| **Multi-Touch (Linear)** | Credit is split evenly across the clicks. | Credit is split evenly across the clicks and modeled impressions. |
| **Algorithmic** | Credit is split across the clicks using the [algorithmic](https://docs.lifesight.io/docs/algorithmic-attribution) channel weights. | The same channel weights are applied across the clicks and modeled impressions. |

Attribution windows apply to modeled impressions exactly as they do to clicks: 1, 2, 7, 14 or 28 days, or lifetime. A modeled impression counts toward a conversion only if it falls inside that conversion's window. Because it's timestamped to the start of its day:

* with a 1-day window, it can only be credited for conversions on that same day;
* a click later on the same day is the later touchpoint under Last Touch.

### Examples

**A click, then a direct visit.** A shopper clicks a Google ad on Monday, comes back directly on Wednesday and buys. On Wednesday they're in the pool, and because Meta had the largest share that day and they've visited from Meta before, they get a modeled Meta impression. With a 7-day window:

| Attribution model | Click-through | View-through |
| :--- | :--- | :--- |
| Last Touch | Google 100% | Meta 100% |
| Multi-Touch (Linear) | Google 100% | Google 50%, Meta 50% |

**Direct visits only.** A visitor with no tracked clicks comes to your site directly on Tuesday and buys the same day. They're matched to TikTok in Tuesday's model.

| Attribution model | Click-through | View-through |
| :--- | :--- | :--- |
| Any | Direct 100% | TikTok 100% |

If a conversion has no clicks and no modeled impressions in its window, it's credited to direct in both views.

## Guardrails

* **Impressions never earn click-through credit.** Click-through numbers come from tracked clicks alone.
* **Credit always adds up to 100%.** In both views, each conversion's credit is split across its touchpoints and totals one conversion. Your total conversions and revenue are the same in both views; only the split between channels changes. View-through mostly moves credit away from direct and organic touchpoints to the channels that delivered impressions.
* **One impression per visitor per day.** A visitor can get at most one modeled impression a day, from one channel, so modeled impressions never outnumber the visitors in that day's pool.
* **Only channels that delivered.** A channel can receive modeled impressions only on days it delivered impressions.
* **A protected direct baseline.** The direct factor caps how many visitors are added to channels beyond those with affinity. Everyone else stays direct.
* **Recorded once.** A day's modeled impressions are kept as they are once recorded.

## Frequently asked questions

**Where does the impression data come from?**\
From your connected ad accounts. Every day, Lifesight ingests delivered impressions, clicks and spend by channel, campaign, ad set and ad from platforms such as Meta, Google Ads, DV360, TikTok, LinkedIn, Snapchat, X, Pinterest, Microsoft and Criteo. View-through modeling uses each channel's daily impression total.

**Do ad platforms tell Lifesight which of my customers saw an ad?**\
No. They report how many impressions ran, not who saw them, which is why exposure is modeled. Any single visitor's modeled impression is an estimate, so read view-through results in aggregate: by channel and over time.

**Which visitors can receive a modeled impression?**\
Anyone who visited your site that day at least once directly, from an organic search or referral, or through a link carrying a search keyword. Each of them can receive at most one modeled impression that day, from one channel.

**How does Lifesight avoid giving ads credit for genuinely direct traffic?**\
Two ways. First, the direct factor holds back part of each day's traffic as a direct baseline: beyond the visitors with affinity, visitors are added to channels only until the channels' shares are filled, and the rest stay direct. Second, click-through reporting is untouched. Switch the Attribution Method to click-through and those conversions show as direct.

**Will view-through inflate my numbers or double-count conversions?**\
No. Each conversion's credit adds up to 100% in both views, so your total conversions and revenue don't change when you switch views; only the split between channels does. Click-through reporting is kept separately and doesn't change.

**Why don't Lifesight's view-through numbers match Meta's or Google's?**\
Each platform reports its own view-through conversions with its own identity graph and attribution windows, and each counts independently, so adding up the platforms' claims often gives more conversions than you actually had. Lifesight credits all channels from one deduplicated view of each customer journey, so its totals reconcile to your actual conversions.

**Can a modeled impression take credit from a real click?**\
Only in the view-through view. There, impressions and clicks follow the same rules: under Last Touch the later touchpoint gets the credit, and under Multi-Touch (Linear) and Algorithmic they share it. Impressions never appear in the click-through view, so each journey's click-based credit is there whenever you switch back.

**What attribution windows apply?**\
The same as for clicks: 1, 2, 7, 14 or 28 days, or lifetime. A modeled impression is timestamped to the start of its day and counts only if it falls inside the conversion's window. The lag between seeing an ad and visiting is modeled as under a day.

**Can I turn view-through off?**\
Yes. Switch the **Attribution Method** setting to click-through. Both views are always kept up to date, so you can switch back and forth on your attribution reports.

**When is view-through data available?**\
Lifesight models impressions once a day for the most recent completed day, as soon as your ad accounts and website tracking are connected. The Lifesight team can backfill earlier periods for which ad data exists.

**Why does view-through match click-through on some days?**\
Usually because no impressions were modeled for that day. Lifesight skips a day when no channel delivered impressions, when your ad accounts reported no clicks, when your site had no direct visits, or when direct visits were at least as many as reported clicks. Impressions modeled on earlier days can still earn credit within their attribution windows.

**How can I get the most accurate view-through results?**\
Keep your tracking consistent. Channel affinity is built from visit history, and a visit counts toward a channel only when it's recognized as coming from that channel. Ad click IDs and consistent UTM tags on every ad make that recognition reliable.

***

**Related:** [Single-Touch Attribution](https://docs.lifesight.io/docs/single-touch-attribution) · [Multi-Touch Attribution](https://docs.lifesight.io/docs/multi-touch-attribution) · [Algorithmic Attribution](https://docs.lifesight.io/docs/algorithmic-attribution)

---
layout: post
title: "More Babies?"
date: 2026-09-21 18:00:00+0800
description: "Understanding the recent birth rate increase of South Korea"
categories: hobby fun demographics
giscus_comments: true
related_posts: true
---

Back in 2022 I was drawing graphs like this:

![graph up to 2020 showing babies per year plummeting to less than a third over forty years](/assets/images/2026-09-21-20-58-19.png){: width="600" .center}

... which, you know, doesn't look great.

So when I went to Korea a few weeks ago, I was surprised to hear a few people who remembered this interest of mine saying "did you hear the birth rate went up? Things are getting better!"

This is how much better they got:

![graph up to 2025 showing small uptick in babies starting from 2024](/assets/images/2026-09-21-20-56-58.png){: width="600" .center}

Notice the little uptick at the end? Yeah, that's the birth rate increase. It's honestly not much and might just be a hiccup before further decline, but maybe it's a start.

Even knowing the rapid birth decline in the late 2010s was unsustainable, I was fascinated at this pause. What has stopped getting worse? How more babies?

Disclosure: all words and analysis are from myself. I got typo checks and a few color recommendations from LLMs.

## Answer 1. It's the firstborns

One quick thing to do is to split the babies by whether they are first-born, second-born, etc.:

![graph stratifying births by birth order showing clear uptick in firstborns, muted increase in secondborns, continued decrease in third and fourthborns](/assets/images/2026-09-21-21-29-49.png){: width="600" .center}

Immediately, we can tell that almost all of the birth increase of 2024 and 2025 has been driven by an increase in first-born children. Second-born children have increased by a very small amount from 2023 (+4,838), while third and fourth- born children have continued decreasing.

As a result, the proportion of first-born children has increased above 60% for the first time:

![proportion graph of nth-borns, showing firstborn proportion increasing above 60% in 2023 at the expense of thirdborns+](/assets/images/2026-09-21-21-35-32.png){: width="600" .center}

The optimistic way of reading this is that there has been a big cohort of newly-weds who are having their first baby. This is in fact supported by statistics we'll see later. Under this reading, we would see the ratio of second-borns recovering in the next few years.

If the firstborn proportion stays roughly similar as years go by, though, this would represent a shift in family patterns that birth rates may not represent, towards even smaller families than in the 2010s. Back then, even despite declining births, _family composition_ itself remained remarkably stable, with firstborns representing about 50% of babies for the thirty-year span of 1990-2020. This might be changing.

## Answer 2. It's from 34+ y/o mothers

An important concept in understanding where babies came from is the age-specific birth rate (ASBR). Age specific birth rate refers to the ratio (babies born to mothers of age X)/(total women of age X) in a specific year. For example:

|Age|Babies Born in 2020|Total women of age|**ASBR**|
|--|--|--|--|
|20|986|642242|986/642242=0.0015|
|25|4530|727952|4530/727952=0.0062|
|30|20439|677332|20439/677332=0.0301|

In case you didn't know, the concept of ASBRs (also called ASFR for fertility rate) is fundamental to the commonly cited "birth rate", because "birth rate" is often Total Fertility Rate (TFR), which is the sum of ASBR values in a particular year. TFR represents the expected number of babies they would have if the current age-specific birth rates held for the entirety of a woman's child-bearing life.

By comparing ASBR statistics over years, we can understand whether women of certain ages are having proportionally more or less babies. There are different ways of visualizing ASBR evolution over time. Here is one visualization I made a while ago showing how ASBR changed from 1981 to 2025:

![heatmap of ASBR over years. It is bright on left and dim on the right, with the heated region gradually moving up as graph goes to right](/assets/images/2026-09-22-22-41-06.png){: width="600" .center}

It shows the birth rate story we saw in the first graph in a different way. We can see two things: the bright part of the graph goes up as we get to recent times, showing how mothers have grown older as time goes by. Second, the heatmap has become noticeably dimmer in the last ten years, representing the decrease in birth rate.

In fact, the recent changes are hard to make out because they are so dim in the heatmap. This won't do, because we are trying to understand the baby rebound of 2025. So I made a new graph, comparing the ASBR of 2020 and 2025:

![bar plot showing ASBR decreasing until age 33, with a consistent increase after age 34](/assets/images/2026-09-22-22-17-57.png){: width="600" .center}

There is a clean pattern: ASBR decreased for mothers younger than age 33, after which there is an increase. This means that women of 33 and younger are less likely to have children (indeed, substantially less likely: the average 30-year-old woman is roughly 25% less likely to have a child), while women of 34 and older are more likely to bear children. Thus, while birth rate is recovering, it isn't exactly a return to prior times; **mothers have become older**.

## Answer 3. COVID rebound: a myth?

A key question: is the baby increase a "COVID rebound"? That is, did potential mothers postpone childbearing during the hectic days of the pandemic, then engage in ["revenge birthing"](https://en.wikipedia.org/wiki/Revenge_buying) in 2024-2025? One way of looking at this is to compare mothers born in 1980, who spent most of their childbearing age prior to COVID, and mothers born in 1990 who were directly impacted by COVID. Specifically, if a strong COVID effect existed, we would see cumulative birth rate for cohorts plateauing then rapidly rebounding to the level of previous cohorts.

Ready to look for that? Brace yourself, because you'll have to squint to see any recent plateau.

![](/assets/images/2026-09-22-23-38-19.png){: width="600" .center}

This paints an even more damning picture than I was imagining. Each successive cohort of women has been having fewer children; there is _no_ birth cohort between 1981-1995 (and indeed up to 2000, although those graphs are short) that had higher births than its previous cohort at a given age. A shocking statistic is that for the 1981-born cohort, the average woman had 0.66 babies by the time she was 30 years old; for the 1995-born cohort, the average woman had 0.22 babies, a decrease of 66% in the span of 14 years - less than a single generation!

How can we square the fact that each cohort is having fewer babies than the one before, yet we see a birth rate increase for 2025? The best way is to remember how birth rates increased for 34+ year-old mothers. That is, a catch-up _is_ happening at later ages. It's just that in the cumulative birth plot above, cohorts have already "lost" so many babies relative to earlier cohorts by the 34 y/o point that the birth rate gains at older ages are simply not enough to bridge the gap.

To conclude, I don't see strong evidence for a COVID effect or a longer-term birth rate increase. Rather, that the 1995 cohort has the lowest ever birth rate at the 30 y/o point casts a pessimistic shadow on the birth rate recovery.

## Answer 4. Marriages are the real COVID rebound

In South Korea, marriage is a large practical barrier/precursor to childbirth. See the graph below: despite a substantial increase in recent times, more than 94% of children are born to married couples.

![graph showing historical out-of-wedlock birth rate  of South Korea, with annotation at maximum point showing maximum value at 5.8%](../assets/images/2026-09-26-16-27-02.png)

So to understand childbirth rates, it is important to understand marriage rates. Which tell different story from births! If one looks at the marriage rate, they show an extremely strong rebound from 2023 (unlike the births case), with the total number of marriages increasing by 25%:

![plot of marriages by year showing marriages dropping by more than 50% from 1990 to 2021, then increasing 25% from 2021 levels](../assets/images/2026-09-26-16-31-31.png)

If we draw the cumulative marriage rate by cohort, there is a clear
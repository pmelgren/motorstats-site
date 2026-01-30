---
title: What's Up With All Those DNFs in the Hybrid Era?
slug: hybrid-era-reliability
date: 2026-01-18T00:00:00-05:00
author: "Pete Melgren"
draft: false
description: Can we understand why so many fewer cars are finishing races in the Hybrid Era?
image: cover.jpg
categories:
    - Analysis
tags:
    - Hybrid
    - DNF
    - Statistical Significance
---

In my [previous post](https://motorstats.io/posts/how-competitive-hybrid-era/), we explored how competitive the racing was in different technical eras of the DW12 chassis. What we found is that the Hybrid Era brought the tightest and most competitive racing of the last decade. This led to some real guilt[^1] on my part. There are a lot of hybrid haters out there, and I didn't want to ruin anyone's off-season by suggesting that IndyCar in its current state might be good and fun to watch.

Luckily - at least for the hybrid haters - we did come across one metric that really made the hybrid look bad. Cars were finishing races at a much lower rate in the Hybrid Era than during any of the previous decade of the DW12 Chassis. After shamelessly suggesting the hybrid has given us good racing, the least I can do is take a deep dive into this low reliability number.

### DNFs Across Eras

First: a quick refresher on the 4 eras we looked at for the DW12 chassis:

* __OEM Aero__: *2015 to 2017* - Each engine manufacturer provided their own Aero kit. No aeroscreen or hybrid power unit.
* __Spec Aero__: *2018 to 2019* - All cars used the same aero kit. No aeroscreen and no hybrid.
* __Aeroscreen__: *2020 to June 2024* - Aeroscreen is introduced. Spec aero still in place. No hybrid power unit.
* __Hybrid__: *July 2024 to 2025* - Hybrid power unit is introduced. Spec aero and aeroscreen still in place.

There is actually a 5th era of the DW12 chassis: from 2012-2014 when the chassis was new but before the OEM aerokit was implemented. But, the data for this era is incomplete – especially in 2012 – so it's being excluded from this analysis.[^2]

Now that we've defined these 4 eras, let's refresh on DNF[^3]  rates for each year since the start of the OEM Aero Era:

<iframe
  src="/plots/DnfByYearEra.html"
  title="DNF Rate by Year and Era"
  loading="lazy"
  style="width:100%;height:525px;border:0;"
></iframe>

The 2nd half of 2024, which was the first (partial) season of the Hybrid Era, had historically high DNF rates. Things got better in 2025, but DNFs in 2025 were still higher than 4 out of 5 seasons in the Aeroscreen Era as well as the entire Spec Aero Era.

### Tight Racing vs Unreliable Cars

The most obvious question we can ask regarding these DNFs is "why?" Maybe the answer actually lies in our previous post. Tight racing means a bunched-up field, with more opportunities for drivers to make mistakes that lead to contact with another car. If that's the case, I'd argue a higher DNF rate is not a bad thing (at least from the fan's perspective). 

If we're seeing more mechanical failures, however, that doesn't feel good for the sport. This would support the hybrid haters' narrative that the DW12 chassis can't handle all this weight and that's causing an unprecedented number of mechincal failures.

So which is it? To answer this question, we can go back to those trusty [results pdfs](http://www.imscdn.com/INDYCAR/Documents/6460/2025-05-26/indycar-race-results.pdf) that IndyCar publishes after each race. Race results will list a *Reason Out* for any car that is not running at the end of the race. From 2015-2025, each of these reasons appeared at least once:

* __Contact__: A car collides with another car or the wall.
* __Mechanical__: A mechanical failure.
* __Off Course__: The car leaves the track (as a result of racing/driver error, not a mechanical error) and is unable to return to the track.
* __Handling__: The car is still running but is retired due to becoming undriveable.
* __Retired__: A generic retirement.
* __DQ__: The car is disqualified.
* __Electrical__: An electrical problem—which I guess IndyCar didn't want to lump into "mechanical" problems.
* __DNS__: Did not start.
* __In Pits__: The car is physically pitted when the race ends - most likely due to some kind of issue that didn't lead to a full retirement.
* __Fire__: Um...

![An Example of a "Fire" DNF](fire3.png)

Some of these classifications are more common than others, and they do seem to change over time as well. Here is how often each classification was used in each era:

| Period     | Contact | Mechanical | Off Course | Handling | Retired | DQ | Electrical | DNS | In Pits | Fire |
|-----------:|--------:|-----------:|-----------:|---------:|--------:|---:|-----------:|----:|--------:|-----:|
| OEM Aero   | 123     | 58        | 9          | 2        | 0       | 0  | 4          | 0   | 0       | 0    |
| Spec Aero  | 78      | 27        | 5          | 4        | 0       | 0  | 0          | 0   | 0       | 1    |
| Aeroscreen | 194     | 65        | 11         | 0        | 1       | 4  | 0          | 1   | 1       | 0    |
| Hybrid     | 87      | 32        | 0          | 0        | 7       | 0  | 0          | 2   | 0       | 0    |

So the vast majority of DNFs are classified as either Contact or Mechanical. Off Course has come up a couple dozen times[^4], but the remaining 7 classifications are rare, appearing at most a handful of times in one or two eras. 

The rare categories aren't going to be very useful towards determining whether the DNFs are due to tight racing or less reliable cars, but we can reasonably group them into broader categories: Contact and Off Course should go together, as these can reasonably be attributed to tight racing, overly aggressive driving, or things of that nature. We'll call this group "crashes". Mechanical, Electrical, and Fire can all be lumped together into a category called "car failures". Handling, Retired, DQ, DNS, and In Pits are all pretty rare and are all difficult to cleanly attribute to either car failure or tight competition, so we'll lump those into a cop-out "other" category.

We'll call the rate at which cars DNF due to a crash reason as _crash rate_ and the rate at which cars DNF due to a car failure as _car failure rate_. We aren't going to spend a lot of time on _other rate_ (sorry), but the sum of all 3 of these we will call _DNF rate_.

So now that we've defined some metrics for a more digestible 3 categories, we can look at the trend by year and see what is contributing to DNFs. If we see a spike in crash rate, then we can blame the tight racing. If we see a spike in car failure rate, we'll conclude the hybrid broke everything. If we see a spike in other rate, I'm taking my ball and going home.

<iframe
  src="/plots/DnfRateByYearType.html"
  title="DNF Rate by Year and DNF Type"
  loading="lazy"
  style="width:100%;height:525px;border:0;"
></iframe>

Crash DNFs are up by a lot in the hybrid half of 2024, but they go back down to average or slightly below average in 2025. Mechanical failures are above average for both seasons of the Hybrid Era, though they are in line with the aeroscreen half of 2024, as well as the entire OEM Aero Era.

### Statistical Significance

So what's our conclusion? If you have an annoying stats friend, or are yourself someone's annoying stats friend, then the "small sample size" alarm bells might be going off in your head right now. The super high crash rate in the hybrid half of 2024 came in only 9 races. The Hybrid Era as a whole is only 26 races old. It's actually quite common for numbers to look inflated in small sample sizes but to even out as the sample size gets larger.

So before we draw any conclusions, we should determine if our sample sizes are large enough for a given number to be meaningful, or if it's just a product of statistical noise. This is what tests of statistical significance are for.[^5] We compare one set of outcomes (such as DNF rate in the Hybrid Era) vs a benchmark set of outcomes (such as DNFs for the entire rest of our sample set), and if the two populations are different enough (as determined by their means and standard deviations), we can deem the populations to be statistically significant[^6].

OK, time for the results. I've run a handful of different tests below. Each test asks whether a certain statistic (DNF rate, crash rate, etc.) is statistically significant over a certain period of time (either the entire Hybrid Era or the hybrid half of 2024). A p-value of .05 or lower is considered statistically significant. Here are the results:

| Test                                   | p-value   | Significant |
|----------------------------------------|-----------|------------:|
| DNF Rate in Hybrid Era                 | 0.071     | No          |
| DNF Rate in 2024 (Hybrid half)         | 0.003     | Yes         |
| Crash Rate in Hybrid Era               | 0.313     | No          |
| Crash Rate in 2024 (Hybrid half)       | 0.014     | Yes         |
| Car Failure Rate in Hybrid Era         | 0.568     | No          |
| Car Failure Rate in 2024 (Hybrid half) | 0.192     | No          |

So the overall DNF rate in the Hybrid Era falls just shy of statistical significance, but the spike in the hybrid half of 2024 is statistically significant at the 5% level(both overall DNF rate and crash rate). In other words, there was a real phenomenon in the 2nd half of 2024 that was leading to more DNFs and more contact. Perhaps – and I'm just spitballing here – the field was getting used to a newer, heavier power unit that was introduced halfway into the season and, as a result, made more mistakes. After some time to get used to the new power unit, however, those contact DNFs went back to normal in the 2025 season.

So what does this say about the theory that tighter racing led to more DNFs? Probably bunk. What does this say about the hybrid haters' theory that the worse, heavier car led to more car failures? Also largely bunk.

Instead, it looks like it's a third thing: namely a major mid-season rule change that led to an adjustment period for drivers and brought more contact. But once the field adjusted, it was racing as usual. And what about the future? Well, if the car failure rate isn't statistically significant, and the crash rate went back to normal in 2025, then there's no reason to think we'll see a substantially higher rate of DNFs persist going forward.

> Cover photo by [sydney Rae](https://unsplash.com/@srz) on [Unsplash](https://unsplash.com/photos/a-black-and-white-photo-of-a-race-car-on-a-track-nLotmcNQ5G0)

[^1]: The author may or may not be Catholic...
[^2]: For convenience's sake, let's just assume the data from this missing era supports whatever you personally think is true about the racing in IndyCar. That's great news for the hybrid haters, who just found 3 years of data that confirms unequivocally that the Hybrid Era ruined our sport! (People who don't mind the Hybrid Era please ignore the previous sentence.)
[^3]: IndyCar doesn't seem to use the term "DNF" in any of their official publications. Instead they tend to say a car is "out" as in "out of the race". This makes some sense given that IndyCar awards points to every car that runs the race, even if they are out after 1 lap. But also it's kind of annoying, and as a former baseball writer, I don't feel like writing about "outs" anymore. So I'm going to stick to using "DNF".
[^4]: Interestingly, there has not been a single Off Course DNF in the Hybrid Era. This actually makes sense as the Hybrid Era is the first time that a car can be restarted from the cockpit. In previous eras, if you went off the track and the car stalled/the engine died, you were done. But with the hybrid, you can turn the car back on and drive back onto the course. RIP Off Course.
[^5]: [*Warning: the following footnote contains a nerdy rant about frequentist statistics. Non-nerds should proceed with caution.*] A lot of people tend to think that "statistical significance" is some kind of magic threshold that makes your data unquestionably correct. In reality, tests for statistical significance essentially just give us a probability that one number is not meaningfully different from a different number. Anything under 5% (i.e. a 95% probability that the numbers are meaningfully different) is typically thought of as being statistically significant, but that's a completely arbitrary number. For instance, if we were talking about driver safety, 5% is WAY too high of a threshold. If, on the other hand, we're asking a question about reliability in the Hybrid Era, and the answer is most likely going to be used only in the context of a bar argument, then 5% is probably fine.
[^6]: [*WARNING: An even nerdier discussion is coming in this footnote. Seriously, if you are the type of person who enjoys having friends or ever having another conversation with a member of the opposite sex, I highly advise you skip ahead.*] It's also worth mentioning that tests for statistical significance are based on a certain set of assumptions that rarely describe the real world, namely the assumption that each individual outcome is an [independent and identically distributed random variable](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables). Mechanical DNFs sort of meet this criteria, but contact DNFs really don't, as "contact" is often with another car and therefore not independent. For that reason, we're definitely going to treat any number at or near the 5% threshold with some skepticism.
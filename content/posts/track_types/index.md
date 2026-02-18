---
title: Track Types Matter!
slug: track-types-matter
date: 2026-02-13T00:00:00-05:00
author: "Pete Melgren"
draft: false
description: Is the answer to everything just "Ovals"?
image: cover.jpg
categories:
    - Analysis
tags:
    - Ovals
---

In the [first](/posts/how-competitive-hybrid-era/) [two](/posts/hybrid-dnfs/) analytical posts of this site, we explored various metrics across technical periods of the DW12 chassis. At the end of each of these pieces, I boldly arrived at some conclusions based on statistically significant results we saw for the Hybrid Era. Specifically, I claimed that the hybrid power unit led to tighter racing than in any other era, and that the introduction of the new power unit halfway through the season led to a spike in DNFs in the 2nd half of 2024.

I posted the second of these articles on reddit - a place where only good things happen - and received a comment wondering if the unbalanced 2024 season could explain these DNFs. I was unsure of what this wise commenter meant, but I guessed it had something to do with track types (this is IndyCar, after all). 

My instinct was that the % of races run on each track type was consistent from year to year, and therefore track type effects would just wash out. But this is a stats blog and I do need content, so I might as well look at the numbers just to make sure:

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/TrackTypeRatesByYear.html"
    title="Percentage of races run on each track type per year"
    loading="lazy"
    style="width:100%;height:550px;border:0;min-width:320px;"
  ></iframe>
</div>

See, I was right. For the most part, the percentage of races run at each track type is pretty consistent from year to year. 2020 is an exception, but the Series had a pretty good reason not to run crowded street races in urban centers. Based on this chart we can expect similar consistency when we look at it for our four technical eras. Then we can wrap this post up early and go back to doom scrolling on Reddit, or however we occupy our time. Right?

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/TrackTypeRatesByEra.html"
    title="Percentage of races run on each track type per year"
    loading="lazy"
    style="width:100%;height:550px;border:0;min-width:320px;"
  ></iframe>
</div>

Well, that's not great. How does the Hybrid Era have a higher % of ovals than any given year in our dataset? How does that math even math? Let's look at the numbers by year for just the hybrid era:

|   Year | Period   |   NRaces |   Oval |   Road |   Street |
|:-------|:---------|---------:|-------:|-------:|---------:|
|   2024 | Hybrid   |        9 |      6 |      2 |        1 |
|   2025 | Hybrid   |       17 |      6 |      7 |        4 |

Oh yeah, almost all of the ovals in 2024 (except the Indy 500) were run in the latter half of the season - after the introduction of the hybrid. So even though the number of ovals is consistent across years, it's way higher for the Hybrid Era due to that imbalance in the 2024 season. Kind of embarrassing that I didn't remember that to be honest.

Well if the Hybrid Era has had significantly more ovals than any other era, could that be to blame for all of the statistical disparity we've seen in the first 2 posts? You do kind of expect ovals to have a more bunched up field and to have more DNFs. Let's revisit the numbers we talked about in the previous posts, but this time with respect to track types instead of technical eras and see whether track types have something to do with it.

### Racing Competitiveness Analysis

We'll start with the first post, where we explored how competitive the racing was. 

I defined a handful of metrics that attempt to describe racing competitiveness. If you'd like a refresher, you can look for the bold text in that [post](/posts/how-competitive-hybrid-era/) or just quickly skim through our NEW(!) stats [glossary](/glossary/).

| Type | Gap | % of Cars on Lead Lap | Gap (Lead Lap Only) | PMov | AdjPMov | Pos At Stake % | Pts At Stake |
|:--|--:|--:|--:|--:|--:|--:|--:|
| Oval | 2.6 | 46% | 1.8 | 6.9 | 4.8 | 45% | 11.6 |
| Road | 4.9 | 73% | 3.7 | 5.5 | 4.7 | 48% | 11.0 |
| Street | 4.2 | 65% | 3.1 | 5.8 | 4.5 | 48% | 12.2 |

Let's run through a quick interpretation of these numbers: 
* __Average Gap__, __Average Gap (Lead Lap Only)__ and  __% of Cars on Lead Lap__  are all explainable by lap times. Since ovals have much shorter lap times, there is less room to develop a large gap before the car behind simply goes down a lap. This also explains why so few cars finish on the lead lap compared to street and road courses.

* __Position Movement__ is larger on ovals. It's tempting to attribute this to more passing, but remember Position Movement can also be a function of DNFs. __Adjusted Position Movement__ (adjPMov) removes the effects of DNFs, and that is only marginally higher on ovals than on Road or Street courses, so most of the PMov we're seeing seems to come from DNFs (more on that later). 

* Finally, __Points at Stake__ and __Positions at Stake__ try to capture how many tight position battles there are at the end of a race. Neither metric is significantly different for Oval races than for Road or Street races.

Based on this, there isn't a lot of evidence that Ovals make the racing significantly more or less competitive. This is fairly consistent with the numbers we ran in the first post that showed a lot of similarity between the Aeroscreen Era and the Hybrid Era. It still seems like the common denominator there is weight, and track types do not play a big factor.

### DNF Analysis

The DNF analysis in my second post is where things get more hairy. The disparity we just saw between PMov and adjPMov suggests that DNFs are more frequent on ovals, so let's see what the numbers actually say.

| Type | NRaces | Total DNFs | DNF Rate |
|:--|--:|--:|--:|
| Oval | 61.0 | 371.0 | 24.0% |
| Road | 71.0 | 143.0 | 8.0% |
| Street | 49.0 | 202.0 | 17.0% |

Fairly intuitive results here. There are more DNFs when there are a bunch of walls to smash into (Ovals and Street courses) and when you are maintaining a high average speed for a longer time (ovals). To really drive the point home, look at this pretty chart:

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/PerRaceDNFDistributionByType.html"
    title="DNF Distribution per Race"
    loading="lazy"
    style="width:100%;height:550px;border:0;min-width:320px;"
  ></iframe>
</div>

So no single road race since 2015 has more than 7 DNFs, meanwhile the median number of DNFs per race on an oval is 6.[^1] I guess the real miracle here is the one oval that had 0 DNFs. Shout out to Marcus Ericsson for running 10 laps down but still finishing in the 2nd race of the 2020 St Louis double header to preserve this distinction.

So now I have a problem. I've already attributed high DNFs in the hybrid half of 2024 to drivers and teams adjusting to the new hybrid power unit, but now we know that ovals have a lot more DNFs than road/street courses and that the hybrid half of 2024 had a hugely disproportionate number of ovals. Is it possible we misattributed those DNFs to the hybrid when it was just a result of track types?

Yes.

But wait a minute, I ran tests for statistical significance and all that. Doesn't that mean that statistically the hybrid did cause the DNFs?

No. Statistical significance means that the high DNFs in the hybrid half of 2024 were a real phenomenon and not just random noise. What we did not answer (statistically at least) was what was causing those DNFs. Essentially there is *correlation*, but not *causation.* If you've ever heard a single person talk about statistics, you've probably heard that correlation does *not* imply causation...

Bad news: we're not going to prove causation. That's really hard and I'd like to get this post published before the 2026 season begins. The good news: we don't need to prove causation, we really just need to prove whether the DNFs should be attributed to the effect of the oval tracks or the effect of the new power unit. A multiple linear regression will easily answer this question for us, essentially acting like running 2 tests for statistical significance at once.[^2]

We'll regress whether a driver DNF'd in an individual race on 2 variables: whether the race was run on an oval and whether the race was run in the hybrid half of 2024. There will also be a constant term which essentially represents all other races. Each variable and the constant will be assigned a weight, and a P-value. We are looking for P-values under .05, and ideally as close to 0 as possible. The weights for all 3 should be positive, indicating that each variable contributes to a higher probability of a DNF. Here are the test results:

| Variable       | Coefficient | P-value |
|----------------|------------:|--------:|
| Constant       | 0.1156      | 0.000   |
| Hybrid Half    | 0.0325      | 0.176   |
| Oval           | 0.1165      | 0.000   |

So the weights tell us that on a road or street circuit in any timeframe other than the hybrid half of 2024, we can expect an 11.6% DNF Rate. Racing on an Oval adds another 11.6% to the expected DNF Rate, and racing in the hybrid Half of 2024 adds another 3.3% to the expected DNF Rate.

Or rather it WOULD mean all of that, except the p-value for the Hybrid Half variable is .17, which is a lot bigger than .05. Essentially this means that when we take into account the higher rate of DNFs due to Ovals, the increase in DNFs during the hybrid half of 2024 is NOT statistically significant and can just be attributed to statistical noise.[^3]

So much for my theory that the DNFs were caused by drivers adjusting to the new power unit. Note to self: _Always_ check track types before jumping to any nice-sounding conclusions.

### Drivers

Ok enough of this deep stats BS. Let's get to the good stuff! It's time to judge drivers by their numbers.

The (arguably) single most important contribution of advanced analytics to sports is the ability to use more stats to win a bar argument. Want to prove that Racer X is better than Racer Y? Well, so far, this blog has given you 0 ammunition to do so.[^4]

But this article is the perfect excuse to break down driver performances by track types. Let's look at some charts that compare average starting position, average finishing position, and DNF Rate by track type. In the interest of making easy-to-read 2D charts, we're going to lump road and street circuits into one category. 

In each of the below charts, the dotted line represents equal performance between ovals and road/street circuits. The further a driver is to the right of that line, the worse they do by that stat on ovals vs road/street courses. The further a driver is the left of that line, the better they do on ovals vs road/street courses. A driver right along that line is fairly equal in both track types.

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/SPOvalvsStreet.html"
    title="Driver Avg Starting Position: Oval vs Road/Street"
    loading="lazy"
    style="width:100%;height:675px;border:0;min-width:320px;"
  ></iframe>
</div>

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/PosOvalvsStreet.html"
    title="Driver Avg Finishing Position: Oval vs Road/Street"
    loading="lazy"
    style="width:100%;height:675px;border:0;min-width:320px;"
  ></iframe>
</div>

* Of all the active drivers, Lundgaard stands out as having the biggest discrepancy between ovals and non-ovals. I wonder if his early success last season - when people were even saying he was going to take Pato's place as the top Arrow McLaren driver - was largely driven by track types.[^5] 

* On a more positive front, remember in 2024 when Ed Carpenter stopped running ovals in the 20 car and let Rasmussen take over those duties? That's looking like a really good decision right now.[^6]

We could come up with a million more takeaways from these charts, but let's also look at DNFs:

<div style="position:relative;width:100%;overflow-x:auto;-webkit-overflow-scrolling:touch;">
  <iframe
    src="/plots/DNFRateRoadStreetvsOval.html"
    title="Driver Avg Positions Gained: Oval vs Road/Street"
    loading="lazy"
    style="width:100%;height:675px;border:0;min-width:320px;"
  ></iframe>
</div>

Again, feel free to choose your own takeaway, but here are mine:
* What I like about this plot (vs the previous two) is that there's a little more going on in the corners. Top drivers are generally bottom-left and the least successful drivers are generally top-right, but the exceptions to that is what really jumps out to me.
* To that point: Santino Ferrucci has 1 DNF in 32 ovals run. How is that even possible? Especially for a guy who has the reputation of being a very aggressive driver.
* Rasmussen (another aggressive driver) also stands out for his low DNF rate on ovals. Apparently if you want to finish a race on ovals it helps to race like an asshole. Though he's only run 10 ovals lifetime so there is probably a small sample size effect here.
* On the other end, what a brutal oval DNF rate for Siegel. Especially for a guy who has spent his whole career in top equipment. 

### Conclusion [^7]

So what have we learned here boys and girls? We've learned that track types are a lot more meaningful when we are talking about DNFs than when we are talking about racing competitiveness. We've learned that Danes named Christian have big track type effects. We've learned that it's easier to finish a race when there aren't walls on every edge of the track to smash into.

Most importantly, however, we've learned that if you make conclusions based on *anything* in IndyCar without first asking yourself whether there are track type effects, you're going to end up looking like a [huge moron](/posts/welcome/#who-is-behind-this). Let's all remember that, especially as the 2026 season begins with one oval in the first six races.

> Cover Photo by [Luca Hooijer]("https://unsplash.com/@luxunderscore) on [Unsplash]("https://unsplash.com/photos/a-curved-road-with-grass-growing-on-the-side-of-it-1jBZY43Jdb4")
      
[^1]: The Indy 500 has more entrants than other races which means that total number of DNFs by track type isn't a perfectly apples to apples comparison. But we're not going to let that get in the way of our pretty chart now are we? Also if we plotted per-race DNF rate instead of total DNFs per race it would show essentially the same thing but the chart would be harder to interpret. 
[^2]: This isn't technically true but for our purposes it's functionally true. Don't @ me stats nerds.
[^3]: For those curious, if we remove the hybrid half term and add a term for street races, the coefficients are constant (Road Races): 8.1%, Ovals: 15.4%, Street Races: 8.9%. In other terms, the baseline DNF rate for a road course is 8.1%, then street races add another 8.9% to that or ovals add another 15.4%.
[^4]: The 2nd-most important aspect of sports analytics is having numbers to prove that you're smarter than everyone. Actually being able to make smarter decisions as a race team ranks somewhere in the teens. 
[^5]: Friendly reminder to ask "is it track types" before coming to any conclusion in IndyCar.
[^6]: Getting the team's first win in 4 years on an oval certainly doesn't hurt Rasmussen on this front.
[^7]: Clever section title right?
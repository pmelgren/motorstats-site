---
title: How Bad (or Good) was the Racing in the Hybrid Era?
slug: how-competitive-hybrid-era
date: 2025-12-31T00:00:00-05:00
author: "Pete Melgren"
draft: false
description: What does the data actually tell us about the quality of racing since the hybrid engine was introduced?
image: cover.jpg
categories:
    - Analysis
tags:
    - Hybrid
    - Aeroscreen
    - Position Movement
    - Adjusted Position Movement
    - Points at Stake
    - Position at Stake
---

Since the hybrid was introduced last July at Mid-Ohio, the public perception has been all about weight. Drivers, fans, the media, your uncle Bill - everyone agrees the Dallara DW12 was never designed to carry that much weight, and the racing has suffered as a result.

It's not all the hybrid's fault, of course - the aeroscreen added a bunch of weight long before the hybrid got here. But the combination of the two is just too much.

Just look at the last lap of the Indy 500 this year compared to the last lap last year. Last year, without the hybrid, we got a dramatic back straight overtake that decided the race and somehow led to everyone liking Pato O'Ward more while cementing Josef Newgarden as an even bigger villain. This year? Sure there was a close battle for P1 on the last lap, but where was the dramatic overtake? Also, unlike last year, only one of the two guys battling for first was in all those Fox commercials. Clearly the hybrid sucks.

Except this is a data blog, and IndyCar has thousands of laps of racing every year. A two-lap sample maybe feels like not enough data to draw a definitive conclusion. So let's dive in.

### Margin of Victory.

__Margin of Victory__ (MoV) - basically the time gap between P1 and P2 at the end of the race - seems to be the go-to metric whenever someone wants to cite how close the racing is. In fact, this post was inspired by an interview IndyCar's Managing Director of Engine Development Darren Sansom gave on the [Pit Pass Indy podcast](https://evergreenpodcasts.com/pit-pass-indy/the-67th-daytona-500-with-josef-newgarden-nascar-president-steve-phelps-and-IndyCar-spring-training-with-darren-sansum-IndyCar-managing-director-of-engine-development). In it, Mr. Sansom specifically cites a low average MoV in the Hybrid Era as evidence that the Hybrid hasn't ruined the racing. (Interview starts around 16:14 mark). 

Obviously we already know he's wrong and that the hybrid *has* ruined the racing, but let's check those numbers just in case...

Before we crunch numbers on the Hybrid Era, though, we need something to compare to. The simplest approach would be to just break things into Hybrid vs Not-Hybrid. If we're worried about weight, though, shouldn't we also break things up by before/after aeroscreen was added? After all, the aeroscreen added close to 20 pounds before the hybrid ever showed up.

OK, so now we have 3 distinct eras: (in reverse chronological order) the Hybrid Era, the Aeroscreen (non-hybrid) Era and the um... Wait what do we call the era before the aeroscreen was introduced. The only good way to name this period is to look backwards another 3 years so we can capture yet another major tech change - specifically when each engine manufacturer brought its own aero kit from 2015-2017.[^1]

Cool, so we now have 4 distinct eras (with names!) we can use for our analysis:

* __OEM Aero__: *2015 to 2017* - Each engine manufacturer provided their own Aero kit. No aeroscreen or hybrid power unit.
* __Spec Aero__: *2018 to 2019* - All cars used the same aero kit. No aeroscreen and no hybrid.
* __Aeroscreen__: *2020 to June 2024* - Aeroscreen is introduced. Spec aero still in place. No hybrid power unit.
* __Hybrid__: *July 2024 to 2025* - Hybrid power unit is introduced. Spec aero and aeroscreen still in place.

With that cleared up, here's what Margin of Victory looked like in each of the 4 eras above:

| Period       | # of Races | Average | Median | Largest |
|--------------|------------|---------|--------|---------|
| OEM Aero     | 49         | 3.5     | 1.5    | 30.3    |
| Spec Aero    | 34         | 4.3     | 2.7    | 28.4    |
| Aeroscreen   | 72         | 3.5     | 1.4    | 30.4    |
| Hybrid       | 21         | 3.0     | 1.7    | 16.0    |

By average (and max) MoV, the Hybrid Era did indeed have the tightest racing. Meanwhile, the Spec Aero Era actually had the largest MoV of any era despite being lighter than both the Aeroscreen Era and Hybrid Era cars. We have done capital-S Science and determined that heavier cars lead to better racing.

### Lead Lap Analysis

You – the clever reader of this blog – might be saying to yourself: "Not so fast! Margin of Victory only looks at the winning and runner-up cars. How is looking at two cars per race a good metric when there are 27+ cars in the field?" You're right, oh wise reader. What if we looked at the margin between all the cars in the field?

OK that's actually more complex than it seems. You can't determine gap between 2 cars that finish on different laps. So first let's just analyze cars that finish on the lead lap.

| Period       | Percent of Cars on Lead Lap | Average Gap Lead Lap Only |
|--------------|-----------------------------|----------------------------|
| OEM Aero     | 63.5%                       | 3.3                        |
| Spec Aero    | 59.3%                       | 3.6                        |
| Aeroscreen   | 62.5%                       | 2.8                        |
| Hybrid       | 58.3%                       | 2.6                        |

__Gap__ here is simply the gap to the car in front at the end of the race. Fewer cars are finishing on the lead lap in the Hybrid era, but those that do are racing closer to each other than in any other era.

There are 2 reasons that we might be seeing a smaller percentage of cars finishing on the lead lap. Either fewer cars are finishing overall, or there is a wider gap between the front and back of the pack. Looking at the percentage of cars that finish, plus the average laps down for non-lead-lap finishers, helps shed some light on which of these possibilities is more liekly:

| Period       | Percent of Cars Finished | Percent of Finishers on Lead Lap | Average Laps Down (Finishers Only) |
|--------------|--------------------------|----------------------------------|-----------------------------------|
| OEM Aero     | 82.8%                    | 76.6%                            | 3.2                               |
| Spec Aero    | 85.7%                    | 69.2%                            | 3.2                               |
| Aeroscreen   | 85.4%                    | 73.2%                            | 2.6                               |
| Hybrid       | 81.2%                    | 71.8%                            | 2.5                               |

Another mixed bag. On the one hand, the cars that finish on the lead lap are in a tighter race in the Hybrid Era than in any other era. On the other hand, fewer finishers are finishing on the lead lap.

Oh yeah, and a LOT fewer cars are finishing at all. Like 29% fewer than in the Aeroscreen era.

Those of you pre-disposed to hate the hybrid I'm sure are licking your chops at that low finishing percentage. I promise we'll look into it, but not in this post. Come on, we're trying to define how "good" the racing is, and races aren't judged on how many cars finish, they're judged on what the cars that finish actually do.

### The Entire Field

So with all of that in mind what else do we want to know? For starters, how close is the racing between cars not on the lead lap? Also what about overtakes, we haven't even looked at a car's ability to move through the pack yet, and that feels important.

Yeah you're right, those things do feel important, and we should look into it. So we're going to define another metric that will do just that:

__Position Movement__ (PMov) is as the absolute difference beteween a car's starting and finishing position. For example, say the car on pole finished in 3rd and the car that started 5th won, then the Position Movement for the pole sitter would be 2 and the position movement for the winner would be 4.

| Period       | Average Position Movement | Average Gap (seconds) |
|--------------|---------------------------|------------------------|
| OEM Aero     | 5.8                       | 4.3                    |
| Spec Aero    | 5.9                       | 13.2                   |
| Aeroscreen   | 6.1                       | 5.1                    |
| Hybrid       | 6.8                       | 6.7                    |

At a surface level, overtaking looks to be strong in the Hybrid Era with cars moving through the pack much more than in any other era. Gap isn't so great, but that might just be explained by faster cars getting around and moving past slower cars more efficiently. 

I'd love to put a bow on thigs and declare the Hybrid Era racing "pretty good"[^2] but I can't ignore all the hybrid haters out there just yet. Remember that finishing % number you read like 30 seconds ago? Remember how bad it was? Turns out cars have a really easy time moving through the pack when nearly 20% of the field ends up retiring early. So that PMov number is almost definitely inflated by DNFs. 

Also do we really care about the gap between cars 3 laps down? For that matter, do we care whether a car is 20 or 25 seconds behind the car in front of it? I mean I don't, and I'm the one writing this blog. So let's fix it, but how?

This is where I pause to address those of you who follow analytics in other sports: right now you're probably thinking to yourself, "Hey, I'm 10 minutes into reading this blog and I haven't been introdued to a single made-up metric yet. So far everything we've talked about has just been number crunching from [IndyCar results pdfs](http://www.imscdn.com/IndyCar/Documents/5498/6456/IndyCar-race-results.pdf). Where are the 7-letter acronyms? Where is the confusing math that turns off casual fans but makes me, the analytics enthusiast, feel smarter?" Well, if that's what you're looking for then you're in luck. Nerd.

And for those of you who are just IndyCar fans desperately looking for any offseason content, I promise I won't be *that* obnoxious with the math and you'll walk away with some decent insight.

### Finisher-Adjusted Metrics

Ok, with that out of the way, let's get back to the DNF problem. I follow IndyCar for the racing and the strategy, not for the attrition. I'm guessing the same is true of the majority of my readers. So let's find a way to measure how much cars move through the field based on speed and strategy, not just because cars in front of them DNFed.

This one's actually pretty easy. If we re-sort the starting grid to exclude the cars that DNF, we can calculate position movement from the on-track racing and not from attrition. To explain, let's revisit my earlier example where the pole sitter finishes 3rd and SP5 wins the race. Now let's say that the car that started SP2 has a mechanical failure and DNFs. In this scenario, we would adjust the starting position of cars 3-27 by 1. So the pole sitter still has a position movement of 2 (since they started in front of the DNFing car) while the winner now has a position movement of 3 (since they ultimately passed the cars in SP4, SP3 and SP1 due to speed/strategy). We'll call this __Adjusted Position Movement__ (adjPMov). 

Hey look, a 7-letter metric! Though technically not an acornym.

| Period       | Average PMov | Average adjPMov |
|--------------|--------------|-----------------|
| OEM Aero     | 5.8          | 4.4             |
| Spec Aero    | 5.9          | 4.4             |
| Aeroscreen   | 6.1          | 4.8             |
| Hybrid       | 6.8          | 4.9             |

One: adjusting for DNFs makes a huge difference. Two: Even when we account for DNFs, the Hybrid Era still has the most Position Movement of any other era. More interestingly, perhaps, the two eras of heavier cars have tighter racing than the two eras that preceed them. Maybe our joke conclusion of "heavier cars lead to better racing" might have actually been correct.

### Improving upon Gap Metrics

Addressing the gap issue also requires a little creativity. If the first 10 cars in a race each finish half a second in front of the next car, then P11 finishes 106 seconds ahead of P12, that's an average gap of 10 seconds per car. 10 seconds per car sounds like a boring race but clearly is not given that P1 and P11 are only separated by 5 seconds. By the same token, a race where every car finishes 10 seconds ahead of the car in front kind of is a boring race. What we need to capture is how many cars finish a competitive distance behind the car they are chasing.

Let's define any gap of 3 seconds or less between two cars as a competitive distance. 3 seconds is a little arbitrary, and certainly we'll want to do some of that capital-S Science later on to refine this number. But for now, 3 seconds feels like a small enough gap that a car could feasibly overtake within a few laps but not so small as to exclude most of the field. When a car finishes within 3 seconds of the car in front, we'll call it a __Position at Stake__ (at Stake) and we can get a sense of how competitive an era is by calculating what percentage of positions are at stake (at Stake %) across an entire era.

But wait! One more thing before we crunch those numbers. We haven't really addressed the problem of "how excited are we really going to get over a competitive battle for P23?" I mean I'd rather P23 and P24 finish 1 second apart vs 30 seconds apart, but I'd even more rather[^3] P1 and P2 finish 1 second apart.

To address this, we need some kind of way of assigning value to each position, with better finishing positions being assigned a higher value. Sadly no such thing exists, so I'm just going to make up an arbitrary system where P1 is awarded 50 points, P2 is awarded 40 points, and subsequent positions are awarded further decreasing points until any car finishing 25th or worse receives exactly 5 points. (OK fine I stole the idea from the *Pts* column of the results data, whatever that means). For each Position at Stake as described above, I'll calculate __Points at Stake__ by determining the base point value (not bonus points) of any Position at Stake. So if P1 and P2 finish 2.3 seconds apart, that is a Points At Stake of 50. We can then get Points at Stake for an entire era by taking total Points at Stake as a percentage of total points available (Points at Stake %). This will help us estimate how competitive the racing is - but weighted by the value of the positiosn being battled over.

OK, explanation over, here are the numbers:

| Period       | At Stake % | Points at Stake % |
|--------------|------------:|------------------:|
| OEM Aero     | 46.3%       | 58.0%             |
| Spec Aero    | 43.3%       | 55.0%             |
| Aeroscreen   | 48.6%       | 61.2%             |
| Hybrid       | 48.8%       | 61.8%             |

Another win for the heavy cars and the Hybrid Era especially. During these 2 eras, more cars finished within 3 seconds of the car in front and those position battles were often towards the front of the pack where more points are awarded.

### Conclusions

We've now looked at a variety of metrics that capture competitive racing and they all seem to point to the same thing. Whether its simply the gap between P1 and P2, a car's ability to move through the field, or the number of cars finishing within striking distance of the car in front, it does seem that the heavier cars - and especially the cars with the hybrid power unit - have resulted in more competitive racing.[^4]

This doesn't mean the hybrid is perfect. I've already highlighted the issues with attrition which should not be ignored. The old engine may have sounded better, and a lighter car might look faster on TV. Maybe you like watching a driver dominate a race and you want more breakawy victories. There are endless reasons why fans watch racing besides overtaking and wheel-to-wheel action. 

But it does seem like IndyCar fans are really proud of having [the greatest racing on earth](https://x.com/wbuxtonofficial/status/1880000721833312297). The numbers are telling us that heavier cars - perhaps too heavy of cars - are a part of that. That may not make the hybrid an unqualified success, but it does feel like time we change the narrative a little and recognize that the hybrid is giving us some good racing.

> Cover photo by [sydney Rae](https://unsplash.com/@srz) on [Unsplash](https://unsplash.com/photos/two-race-cars-speed-around-a-curved-track-fuUDSlf3gOY)

[^1]: If you are up with your semi-recent technical history you're probably saying to me right now "Hey idiot, why don't you just start at the beginning of the DW12 era in 2012?" Good point. But sadly, the [data](https://IndyCar.com/results) I'm using here isn't complete until 2013, so I wouldn't be able to accurately summarize those first 3 seasons for an apples-to-apples comparison with the other eras.
[^2]: Shout out to [Jon Bois](https://www.youtube.com/playlist?list=PLUXSZMIiUfFSCYW1o-4whWtepyVlsfuCC)
[^3]: That's definitely not a phrase.
[^4]: I'm by no means an engineering expert, so I can't say with any certainty why this might be. One reasonable explanation is that weight is a form of downforce that isn't subject to dirty air, so a heavy car might actually have more ability to closely follow the car in front without losing too much grip on the corners. Or it could be that heavier cars are slower and have less ability to break away in clean air. I'm sure you have your own theory.
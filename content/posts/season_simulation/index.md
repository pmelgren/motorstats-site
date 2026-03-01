---
title: Predicting the 2026 season
slug: sim-results-2026
date: 2026-03-01T00:00:00-05:00
author: "Pete Melgren"
draft: false
description: I built an IndyCar simulator. Now it's your chance to pick the results apart!
image: cover.jpg
categories:
    - Analysis
    - Simulation Model
tags:
    - Alex Palou
    - Will Power
    - Josef Newgarden
    - Denis Hauger
    - Not AI
---

On the eve of the 2026 season opener, I wanted to do something different: My approach to my first three posts was to pick a topic then analyze stats from previous seasons to learn more about how IndyCar works. That's all well and good for January, but we're mere hours away from the first race of 2026. I can't imagine anyone wants to read in-depth analysis of stuff that happened last season - that's offseason content and it's the on-season baby!

One slight issue there: with the 2026 season not having happened yet, I don't have actual data to analyze. The solution: I'll just make up my own stats. That seems a lot easier than having to use real data right? 

It turns out in the world of motorsports analytics, "making up your own stats" is called "simulation" and it's actually way harder than looking at historical data. I really wish someone would have told me that a few weeks ago, but here we are. 

So yes, I built an IndyCar simulation model and I wanted to share the results as a season preview. 

I know my nerdier readers will be eager to hear the details of how the model arrived at its conclusions. But as a favor to those of you who aren't that nerdy and actually talk to girls (or boys[^1] ) - I wanted to share the exciting top-line results first.

So, without further delay, the winner of the 2026 season will be:

__Alex Palou__

OK good. Any other name there means I royally screwed something up. Good to know at the very least the model is able to figure out the obvious. 

## About the Model

So before I show you the entire range of outcomes from my simulation model, I need to give a little context on what the model is and how it works. That's the bad news. The good news: I'll save the super in-depth stuff for later and we'll keep it high-level today. The even better news: if you really don't care you can just scroll down.

So how does the model work? At a high level, we use predictive statistical models as much as possible, and only rely on monte carlo simulation when a predictive model won't do. The statistical models are machine learning[^2] tools that look at variables related to the drivers, teams, and tracks, then predict each driver's starting position, whether they finish a race, what that driver's finishing position will be.

Where the simulation comes in is the need to use outcomes from one model to train the next. Starting position is an input into whether a driver DNFs, but I don't yet know starting position for every driver and every race of 2026. So what I can do is use my starting position model to predict where each driver will start a given race, then use that as an input to predict whether each driver will finish the race. And once I have a prediction of whether a driver will finish a race, I can use that to further predict what the driver's final finishing position will be. 

To get realistic data, however, there also has to be an element of randomness (or luck) in my predictions. A lot of things can happen on track that are nearly impossible to anticipate - so I used the historic randomness[^3] for a given team, driver, and track type to come up with more realistic predictions. 

Of course, that randomness can swing things by a lot in a given season  so I simulated 10,000 seasons and aggregated the results in order to arrive at a view of what the model thinks can and most likely will happen in the 2026 season.

## Simulated Results.

So at a high level - here is what my model predicted would happen in the 2026 season over 10,000 simulations:

| **Driver**|Average Season Points|Race Finish Rate|Average Starting Position|Average Finishing Position|Wins per Season|Poles per Season | 
|:---------------------|----------:|-------------:|--------:|--------:|----------:|-----------:|
| **Palou, Alex**          |     643.8 |        85.3% |     5.2 |     6.9 |       4.4 |        3.6 |
| **O'Ward, Pato**         |     587.5 |        85.2% |     5.5 |     7.6 |       2.5 |        4   |
| **Lundgaard, Christian** |     502.7 |        85.1% |     8.1 |     9.3 |       1.2 |        1.7 |
| **McLaughlin, Scott**    |     499.9 |        85.3% |     9.3 |    10.1 |       1.9 |        1.4 |
| **Dixon, Scott**         |     466.1 |        85.4% |    12.4 |    10.2 |       0.7 |        0.2 |
| **Malukas, David**       |     450.4 |        85.1% |     8.5 |    11.4 |       1.1 |        1.6 |
| **Kirkwood, Kyle**       |     441.1 |        85.2% |    10.6 |    11.1 |       0.9 |        0.7 |
| **Newgarden, Josef**     |     437.2 |        84.9% |    10.5 |    11.6 |       1   |        0.9 |
| **Armstrong, Marcus**    |     419   |        85.3% |     9.6 |    11.7 |       0.5 |        0.6 |
| **Rossi, Alexander**     |     400.3 |        85.0% |    12.8 |    12.3 |       0.5 |        0.2 |
| **Rosenqvist, Felix**    |     392.4 |        85.2% |     9.2 |    12.4 |       0.3 |        1   |
| **Simpson, Kyffin**      |     390   |        85.1% |    14.3 |    12.6 |       0.4 |        0.1 |
| **Ferrucci, Santino**    |     379.2 |        85.0% |    15.4 |    13   |       0.5 |        0.5 |
| **Rasmussen, Christian** |     376.7 |        85.0% |    15.7 |    13   |       0.4 |        0   |
| **Siegel, Nolan**        |     360.5 |        84.7% |    11.2 |    13.4 |       0.2 |        0.5 |
| **Ericsson, Marcus**     |     345.5 |        84.9% |    12.4 |    14   |       0.2 |        0.2 |
| **Veekay, Rinus**        |     343.5 |        85.1% |    16.4 |    14.4 |       0.4 |        0.1 |
| **Grosjean, Romain**     |     336.9 |        84.2% |    13.8 |    14.3 |       0.2 |        0.1 |
| **Power, Will**          |     329.4 |        85.0% |    13.3 |    14.5 |       0.1 |        0.1 |
| **Robb, Sting Ray**      |     322.9 |        84.8% |    19.3 |    14.8 |       0.2 |        0   |
| **Rahal, Graham**        |     294.5 |        85.2% |    14.5 |    15.7 |       0   |        0.2 |
| **Foster, Louis**        |     270   |        84.1% |    17.9 |    16.5 |       0   |        0   |
| **Schumacher, Mick**     |     233.8 |        83.0% |    18.7 |    18.4 |       0   |        0   |
| **Collet, Caio**         |     226.3 |        81.5% |    19.8 |    18.9 |       0   |        0   |
| **Hauger, Denis**        |     219.8 |        81.2% |    23.1 |    19.1 |       0   |        0   |
| **Carpenter, Ed***       |      19.2 |        76.5% |    10.8 |    15.2 |       0   |        0   |
| **Hunter-Reay, Ryan***   |      18.4 |        75.7% |    13.5 |    15.4 |       0   |        0   |
| **Castroneves, Helio***  |      17.7 |        76.7% |    15.4 |    15.9 |       0   |        0   |
| **Harvey, Jack***        |      12.1 |        77.3% |    26   |    20   |       0   |        0   |

| **Driver**|Average Championship Standing |   Total Championships |  Total Indy 500 Wins |   Best Standings Finish |   Worst Standings Finish |
|:---------------------|---------------:|----------------:|--------------:|-------:|--------:|
| **Palou, Alex**          |            1.5 |            6766 |          2042 |      1 |      15 |
| **O'Ward, Pato**         |            2.3 |            2506 |          2047 |      1 |      16 |
| **Lundgaard, Christian** |            4.8 |             249 |           879 |      1 |      20 |
| **McLaughlin, Scott**    |            5.1 |             338 |           383 |      1 |      21 |
| **Dixon, Scott**         |            6.5 |              45 |           414 |      1 |      21 |
| **Malukas, David**       |            7.7 |              48 |           598 |      1 |      23 |
| **Kirkwood, Kyle**       |            8.1 |              22 |           241 |      1 |      23 |
| **Newgarden, Josef**     |            8.5 |              17 |            99 |      1 |      23 |
| **Armstrong, Marcus**    |            9.6 |               6 |           293 |      1 |      23 |
| **Rossi, Alexander**     |           11.1 |               2 |           530 |      1 |      24 |
| **Rosenqvist, Felix**    |           11.7 |               0 |           176 |      2 |      23 |
| **Simpson, Kyffin**      |           11.9 |               0 |           221 |      2 |      24 |
| **Ferrucci, Santino**    |           12.8 |               1 |           550 |      1 |      25 |
| **Rasmussen, Christian** |           13   |               0 |           363 |      2 |      25 |
| **Siegel, Nolan**        |           14.4 |               0 |           148 |      2 |      24 |
| **Ericsson, Marcus**     |           15.8 |               0 |            86 |      2 |      25 |
| **Veekay, Rinus**        |           15.9 |               0 |           340 |      3 |      25 |
| **Grosjean, Romain**     |           16.5 |               0 |            53 |      4 |      25 |
| **Power, Will**          |           17.1 |               0 |            48 |      3 |      25 |
| **Robb, Sting Ray**      |           17.6 |               0 |           132 |      3 |      25 |
| **Rahal, Graham**        |           19.9 |               0 |             3 |      8 |      25 |
| **Foster, Louis**        |           21.6 |               0 |             0 |     13 |      25 |
| **Schumacher, Mick**     |           23.4 |               0 |             3 |     16 |      25 |
| **Collet, Caio**         |           23.7 |               0 |            11 |     12 |      25 |
| **Hauger, Denis**        |           24.1 |               0 |             1 |     15 |      25 |
| **Carpenter, Ed***       |           27.2 |               0 |           157 |     26 |      29 |
| **Hunter-Reay, Ryan***   |           27.3 |               0 |           115 |     26 |      29 |
| **Castroneves, Helio***  |           27.4 |               0 |            67 |     26 |      29 |
| **Harvey, Jack***        |           28.1 |               0 |             0 |     26 |      29 |

<div style="font-size: 0.95em; color: #666; margin-top: -10px; margin-bottom: 20px;">
*Indy 500 one-off driver.
</div>

Let's discuss a few of the more surprising results here and how we should interpret them:

For those of you tired of seeing __Alex Palou__ dominate the series: the model has someone else winning the championship about 1/3 of the time, which is actually not very many at all. By far the 2nd-most likely champion is O'Ward, with Lundgaard, and McLaughlin getting in the mix on occasion. 

__Will Power__ is by far the biggest shocker here. The model doesn't just dislike him, it seems to downright hate him, predicting Power to be the 19th-best driver out of 25. I can't say with absolute certainty why that is, but I do know that Team Penske is one of the most impactful features in the model. That means that if the model sees a driver in a Team Penske car, the model is more likely to attribute the success of that car to Penske and less likely to attribute it to the driver. 
This does make some intuitive sense - Penske has a really strong team identity and unlike other top-tier teams, they rarely run an entry that is anything short of highly competitive. The model had 0 data points of Power in any car other than Penske, and since the model considers team Penske to be highly competitive, it must in turn give less credit to Penske's drivers. So now that we are trying to predict Power's performance in a car the model likes less, you can see how his predicted results would be poor.
Whether you agree with the model is an entirely different matter. For my part, I think Power will do better than 19th, but if he has a terrible year, then hopefully the readers of this post will be *slightly* less shocked than most.

Another shocker is __Josef Newgarden__ getting no love at the Indy 500. Yes, a single-race prediction is very noisy, but come on. The guy won 2 of the last 3 Indy 500's and yet the model only sees him winning it 99 times in 10,000 iterations. Even Nolan Siegel is given credit for winning it 148 times in 10,000 iterations. This is most likely a similar story to Power when it comes to guys who have spent most or all of their career in a Penske car getting very little individual credit.

Rookies like __Denis Hauger__, __Caio Collet__, and __Mick Schumacher__ are inherently hard to predict because they have never appeared in the series before. To account for our lack of data on these 3, I use a technique from other sports known as "player comps". The idea is to select a player that you expect to be similar to the rookie, then predict the rookie as if he is that player (all other data related to the rookie besides identity is kept the same). Unfortunately, the player pool in IndyCar is very shallow, so perfect comps don't exist. For Hauger and Collet, I used recent IndyCar drivers who had similar results to those 2 in Indy NXT. Hauger's dominant 2025 looked a lot like Louis Foster's dominant 2024. Collet's runner-up campaign in 2025 was most reminiscent of Jacob Abel's Indy NXT career. For Schumacher, I went with the former F1 route and used Ericsson as his best comp. All three of these comps have the added benefit of reaching these career milestones at similar ages.
I didn't want to overweight these subjective comps, however, so half of the predictions used comps and half just used an unspecified driver. The result of this technique was a slight improvement in the standings for these three drivers vs just using the unspecified driver. Overall, however, the model is very unlikely to reward rookie drivers. So in many of the simulations, Hauger, Collet, and Schumacher finish bottom 3 (before the Indy 500 one-offs) in some order[^4]. 

## Conclusion:

So what are we to make of all of this? Hopefully there is something to learn from these simulated outcomes, and maybe it'll provide some interesting context as the actual 2026 season actually unfolds.

If you don't agree with the predictions on Power, Newgarden, Hauger, or anyone else, however, that's ok. The goal here was simply to provide statistically-based predictions of the 2026 season. The model is reasonably predictive and built on very sound principles, but it's by no means perfect. So if you would like to criticize it or even just nit-pick a few outcomes you are welcome to. Hopefully, in time, the model will improve both due to more data coming in and more time spent really tweaking and fine-tuning it.

In the meantime, however, I hope you have enjoyed checking out my made-up data. And if you haven't you can always just make up your own!


> Cover Photo by [Umberto]("https://unsplash.com/@umby?utm_source=unsplash&utm_medium=referral") on [Unsplash]("https://unsplash.com/photos/blue-circuit-board-jXd2FSvcRr8?utm_source=unsplash&utm_medium=referral")    
      
[^1]: I mean [Motorsports IS for the Girls Now](https://www.jalopnik.com/motorsport-is-for-the-girls-now-1851473854/). (Shout out to Elizabeth Blackstock who freakin' rocks).
[^2]: Is Machine Learning the same thing as AI? That depends on who you ask. Technically AI is more focused on replicating human behavior like speech or listening or vision. Machine learning is more focused on advanced techniques in statistical modeling. But in 2026, AI is such a buzzword that a lot of things get lumped in with it. Also if you are an investor looking to throw millions of dollars at any half-baked idea involving AI, then yes this is AI and you know how to get a hold of me.
[^3]: In this case, we replicated randomness by looking at the actual historical difference between what the model would have predicted on past data and what actually happened - also known as residuals. We used residuals from drivers, teams, and track types, then weighted them by how much the model valued each variable. 
[^4]: By the time this goes up, Hauger will have already qualified on the 2nd row for St. Pete, so that bottom-3 prediction isn't looking great so far.
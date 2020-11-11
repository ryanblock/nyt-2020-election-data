CulturalHusbandry
@APhilosophae
The following information is provided via an anonymous data scientist and another anonymous individual who wrote a script to scrape the national ballot counting time series data of off the
@nytimes website.

4:12 PM Nov 8, 2020
6.8K Retweets
2.9K Quote Tweets
12.2K Likes

-----

CulturalHusbandry
@APhilosophae Nov 8
Replying to
@APhilosophae
This is based on their proprietary "Edison" data source which would ordinarily be impossible to access for people outside the press.

-----

CulturalHusbandry
@APhilosophae Nov 8
The CSV is available here:
http://s000.tinyupload.com/?file_id145669d14566999163698825215
And the script to generate it is here:
https://pastebin.com/NkYXrJEX

-----

CulturalHusbandry
@APhilosophae Nov 8
I suggest that everyone back up both of these files, bc this is an extremely important data source, and we cant risk anyone taking it down.

-----

CulturalHusbandry
@APhilosophae Nov 8
What we are looking at will be time series analysis and you will see that it is extremely difficult to create convincing synthetic times series data. By looking at the times series logs of the ballot counting process for the entire country, we can very easily spot fraud.

-----

CulturalHusbandry
@APhilosophae Nov 8
One of the first things noticed while exploring the dataset is that there seems to be an obvious pattern in the ratio of new #Biden ballots to new #Trump ballots.

-----

CulturalHusbandry
@APhilosophae Nov 8
As we can see on this log-log plot, for many of the counting progress updates, we see an almost constant ratio of #Biden to #Trump. It's such a regular pattern that we can actually fit a linear regression model to it with near-perfect accuracy, barring some outliers.

-----

CulturalHusbandry
@APhilosophae Nov 8
How could this be possible? Is this a telltale sign of fraud? Surprisingly, as it will be shown, the answer is no! This is actually expected behavior. Also, we can use this weird pattern in the ballot counting to spot fraud!

-----

CulturalHusbandry
@APhilosophae Nov 8
Here is the same pattern for Florida. We see this linear pattern again.

-----

CulturalHusbandry
@APhilosophae Nov 8
and again

-----

CulturalHusbandry
@APhilosophae Nov 8
and again

-----

CulturalHusbandry
@APhilosophae Nov 8
and again all over the country. What appears to be happening is that points on the straight line are actually mail in votes. The reason they're so homogeneous across with respect to the ratio of #Biden vs #Trump votes is that they get randomly shuffled in the mail...

-----

CulturalHusbandry
@APhilosophae Nov 8
like a deck of cards. Since the ballots are randomly mixed together during transport, spanning areas occupied by multiple voting demographics, we can expect the ratio of mail-in #Biden ballots to mail-in #Trump ballots will remain relatively constant over time...

-----

CulturalHusbandry
@APhilosophae Nov 8
and across different reporting updates.

Lets dig a little deeper into this:

-----

CulturalHusbandry
@APhilosophae Nov 8
Here is a plot of the same Florida voting data, but this time it's the ratio of #Biden to #Trump ballots, versus time. What we see is that the initial ballot reportings are very noisy and "random".

-----

CulturalHusbandry
@APhilosophae Nov 8
The initial reporting represents in-person voting. These vote reports have such large variation bc in-person voting happens across different geographic areas that have different political alignments.

-----

CulturalHusbandry
@APhilosophae Nov 8
We can see this same pattern of noisy in-person voting, followed by homogeneous mail-in reporting in almost all cases.

-----

CulturalHusbandry
@APhilosophae Nov 8
What we see in almost all examples across the country is that the ratio of mail-in Dem to Rep ballots is very consistent across time, but with the notable drift from Dem to slightly more Rep.

-----

This slight drift from D to R mail-ins occurs again and again, and is likely due to outlying rural areas having more R votes. These outlying areas take longer to ship their ballots to the polling centers.

-----

CulturalHusbandry
@APhilosophae Nov 8
Now we're getting into the really good stuff. When we see mail-in ballot counting where there isn't relatively stable ratios of D and R ballots that slightly drift R, we have an anomaly! Anomalies themselves are not necessarily fraud, but they can help us spot fraud more easily.

-----

CulturalHusbandry
@APhilosophae Nov 8
Now let's look at some anomalies:

-----

CulturalHusbandry
@APhilosophae Nov 8
This is the Wisconsin vote counting history log. Again, on the Y axis we have the ratio of D to R ballots in reporting batch, and on the X axis we have reporting time.

-----

CulturalHusbandry
@APhilosophae Nov 8
Around 4am there, there is a marked shift in the ratio of D to R mail-in ballots. Based on other posts in this thread, this should not happen. This is an anomaly, and while anomalies are not always fraud, often they may point to fraud.

-----

CulturalHusbandry
@APhilosophae Nov 8
so what happened just before 3am CST in Wisconsin? This did!
Quote Tweet

Matt Smith
@mattsmith_news Nov 4
Milwaukee’s 169,000+ absentee ballots en route to county election officials

-----

CulturalHusbandry
@APhilosophae Nov 8
Around 3am Wisconsin time, a fresh batch of 169k new absentee ballots arrived. They were supposed to stop accepting new ballots, but eh, whatever I guess.

-----

CulturalHusbandry
@APhilosophae Nov 8
By 4am the D to R ratio was all thrown out of whack. That is because these ballots were not sampled from the real Wisconsin voter population, and they were not randomized in the mail sorting system with the other ballots. They inherently have a different D to R signature...

-----

CulturalHusbandry
@APhilosophae Nov 8
than the rest of the ballots quite possibly bc additional ballots were added to the batch, either through backdating or ballot manufacturing or software tampering. This of this being kind of analogous to carbon-14 dating, but for ballot batch authenticity.

-----

CulturalHusbandry
@APhilosophae Nov 8
lets look at another anomaly:

-----

CulturalHusbandry
@APhilosophae Nov 8
Here is Pennsylvania's vote counting history. For the first part of the vote counting process, we see the same pattern for mail-in ballots that we've seen in every other state in the country, which is relatively stable D to R ratio that gradually drifts R as more ballots...

-----

CulturalHusbandry
@APhilosophae Nov 8
come in from rural outlying areas.

But then as counting continues, the D to R ratio in mail-in ballots inexplicably begin "increasing". Again, this should not happen, and it is observed almost nowhere else in the country, because all of the ballots are randomly shuffled...

-----

CulturalHusbandry
@APhilosophae Nov 8
in the mail system and should be homogeneous during counting. The only exceptions to this are other suspect states that also have anomalies.
Again, this is evidence of ballot backdating, manufacturing of software tampering.

-----

CulturalHusbandry
@APhilosophae Nov 8
Lets look at another anomaly:

In Georgia we see pretty much the same story as Pennsylvania: increasing fractions of mail-in D ballots over time even though it defies logic and we see this pattern no where else in the country.

-----

CulturalHusbandry
@APhilosophae Nov 8
In Michigan, we see a combination of Wisconsin strangeness, together with the GA/PA weirdness. We see both signs of contaminated ballot dumping, and ballot ratios drifting toward dems when they should not be.

-----

CulturalHusbandry
@APhilosophae Nov 8
Virginia:

-----

CulturalHusbandry
@APhilosophae Nov 8
Now in fairness, VA is the only state out of the 50 that has anomalies but has not had accusations of voter fraud, yet. I think this is the exception that proves the rule. Yet to figure out what causes this anomalous shift, but here it is so no one accuses me of holding it back.

-----

CulturalHusbandry
@APhilosophae Nov 8
Lets wrap this up: It appears Dems shot themselves in the foot bc making everyone do mail-in ballots actually makes it easier to catch mail-in ballot fraud. Bc all of the ballots go through the postal system, they get shuffled like a deck of cards, so we expect reported...

-----

CulturalHusbandry
@APhilosophae Nov 8
ballot return to be extremely UNIFORM in terms of D vs R ratio, but to drift slightly towards R over time bc some of those ballots travel farther. This pattern proves fraud and is a verifiable timestamp of when each fraudulent action occurred.

-----

CulturalHusbandry
@APhilosophae Nov 8
Please disseminate as necessary. Good luck. Stay safe. Be kind to your neighbors.

#Epsteindidntkillhimself

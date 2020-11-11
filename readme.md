# NYT 2020 election data analysis

Some analysis of the NYT 2020 election dataset as scraped from their static JSON API. The latest scraped csv [can be found here](./data/nyt_ts.csv).

An example of that data:
```json
{
  "vote_shares": {
    "bidenj": 0.82,
    "trumpd": 0.165
  },
  "votes": 231201,
  "eevp": 1,
  "eevp_source": "edison",
  "timestamp": "2020-11-04T04:13:01Z"
},
```

We are to extrapolate from the total votes and vote shares how many votes went to each candidate.

From what I can tell, `eevp` field is a flag signifying the data point comes after 90% of the total expected vote count.


## Caveats + notes

This (amateur) analysis is in partial response to another amateur analysis [on Twitter](https://twitter.com/APhilosophae/status/1325592112428163072) in a series of tweets supposedly based on this dataset, courtesy of `anonymous data scientist and another anonymous individual who wrote a script to scrape the national ballot counting time series data`.

There is nothing about the psuedonymous `CulturalHusbandry` that's remotely trustworthy with regard to hypotheses about election fraud, and as a former journalist, you'd be a fool to trust unvetted, anonymous sources on the internet. Additionally, much of Twitter thread in question (archived in the [twitter dir](./twitter)) conveniently favors a specific narrative, and **selectively presents vague, barely labeled representations of data to support that narrative**.

The thread focuses largely (or solely in some cases) on states that were prevented by Republicans from counting mail-in ballots in advance, which were known to lean heavily on Biden – why? Because for some reason in the US, the spread of COVID has been politicized by Republicans, and Trump spent months telling his prospective voters not to vote by mail.

Further, this mass voter fraud hypothesis **does not cite specific data points that can only be explained by fraud**, or put another way, **it offers no alternate explanations** (such as geographical distribution, mail-in balloting, out of order counting, mislabeled data, etc) – this is a classic tactic to drive a narrative toward a predetermined conclusion.

Finally, the dataset itself poses a number of issues that strike me as making it difficult (or possibly impossible) to arrive at any of the same conclusions this individual arrived at:

- **Missing FIPS (location) data** - None of the data from the returns is location stamped with US-standard FIPS codes, so we don't know whether the data points are mail-in, or correspond to one (or more) counties
- **Inexact vote numbers** - the data is presented in vote shares, not in raw tabulated numbers. In large data sets this can cause massive amounts of rounding to accmuluate
- **Variance in reporting time** – as we now know, not all counties reported results the same day they were counted, and that phenomena does not appear to be denormalized in the timestamps
- **Non-reproducible results** - the code and formulae used to derive results posted to Twitter were not shared; scraping this data and running it, I see only passing similarities

Out of curiosity I'll probably continue researching this dataset a bit more, but the tl;dr...


### tl;dr

You probably shouldn't believe internet conspiracy theories. But if you must, I have a fresh supply of bridges to sell you.


## Thanks

💕💕💕 to [Cameron Marlow](https://github.com/cameronmarlow) for helping me suck less with Pandas!

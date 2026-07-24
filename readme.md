# Bill Scraper Memo & Methodology:

## Bill scraper memo:
If I ran my bill scraper for a year, it would show some interesting trends in the New Jersey Senate. Particularly, I could do some classification or else keyword/sentiment analysis of bill texts to find the highest-priority issues taken up by the senate in that legislative session. It would be interesting, too, to compare the trends in the Senate and the House (would require two scrapers or an expansion of my current scraper) to see how much they agree and which bills pass both chambers vs. being stuck in one or the other.

Having this legislative information as a standardized data set would also let me identify the most (or least) active legislators – those who propose the most bills in a given session, and to look for common differences in bills proposed between democratic and republican senators.

I would also be interested in comparing the breakdown of legislative activity per session to states where the legislative sessions do not run year-round. I might expect that legislative activity would be more evenly distributed in a place like New Jersey where there is no break between sessions, so thereby no delay if a legislator waits to propose a bill until the new session starts.

Tracking bills in multiple stages through the senate could also reveal some interesting trends in the general life cycle of bills in the NJ state legislature (eg. which bills go through the legislature the fastest? Are budget bills a higher priority? Do bills addressing hot-button political topics become subject to more discussion on the floor?)

It would be most interesting, I think, to run this scraper for one year, starting and ending with a legislative session. Even more interesting, possibly, would be to either run the scraper for several years or else to run it on previous legislative sessions to be able to compare these trends across distinct sessions.

<br>
<br>

## Bill Scraper Methodology:

### Scope:
I will be scraping bills from the New Jersey State Senate, as found on the NJ State Legislature bill search page. I’m specifically focusing on the Senate, though it looks like a small tweak in the API link would allow me to search results for the House.

### Technique:
I was able to find the API link that returns my search results, and am using that in conjunction with a changelog to ensure that I am only scraping results when they contain new information that is not in my data set.

### Data Integrity:

I’ll be tracking:
#### Individual columns:
- Identifying Information
- Bill #
- Any companion bill #s
- Session #
- The url to the bill on the page
- Overview Senate Info
- The committee the bill is assigned to
- The current status
- The last action taken on the bill
- The bill type (will always be s in this dataset for “senate” but i think it’s Helpful to include in case i did want to merge this with house bills)
- The number of primary sponsors

#### Nested Lists (each of these has multiple fields with more information)
- History (list of previous bill actions)
- Prime Sponsors/Co-Sponsors
- Documents associated with the bill
- Committee votes 
- Floor votes
- Committee roll call votes
- Floor roll call votes

Many of these columns will be empty (particularly the vote databases) until the bill is nearing its completion, and I’m planning to just leave them blank until data exists to fill them.

### Analysis:
I’m particularly interested in the history of each of the bills and later of doing some analysis on the dataset to parse the texts of the individual bills. Also, as mentioned above, the information about prime and co-sponsors will be interesting to analyze to better understand the legislative activity of various members of the New Jersey Senators.

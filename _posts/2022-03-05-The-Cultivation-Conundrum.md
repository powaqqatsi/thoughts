Below is a deeply flawed essay I wrote back in the Fall of 2019. If you want to read my deeply flawed work, for whatever reason, go on ahead. There might be some crumb of insight below, but I'm mainly posting this for curious family.

I'd been working through the Bible at the time of writing, fascinated with the origins of states, and what I came across was eye opening. Reading with an atheistic lens, I saw a priest class project superstition to carve out a foothold of power above the 12 tribes' leaders. Do this to stay clean. Do that, and you'll become unclean. (Cleanliness here was both literal and figurative, a binary indicator of whether a person was or was not in the good graces of the Jewish God (and their society at large)). 

While many laws seemed entirely arbitrary and pointless (besides stuffing priestly pockets), quite a few felt like the works of an ancient FDA or CDC. Additionally, there seemed to be a deliberate finger on the pulse of agricultural production. Wading through the superstition-laden language in their books of history and law, I saw taxation, centralized yield monitoring, and load management of private land.  

At the time, I had naively figured that there was a good reason for this co-opting of the means of production. That's what the essay below seeks to discover. But, after reading [Against The Grain](https://en.wikipedia.org/wiki/Against_the_Grain:_A_Deep_History_of_the_Earliest_States) I'm now of the opinion that centralized control almost certainly existed for the prosperity of the ruling elite, rather than population well-being (although one can lead to the other).

There's also a pretty obvious flaw in this analysis which I'm just seeing today. Skip down to the piece if you want to try to find it yourself. I'm guessing it shouldn't be too hard to spot the bad assumption! Found it? Okay, assuming (hoping) there's only one, I think this is what you noticed: Crop yields across a society are not independent events, but rather inter-linked, since weather is consistent across large regions of land. This makes the analysis useless for considering a gap between personal and communal decision making :). Maybe this piece could be revived to tell us something useful about inter-state relations in this age? But I don't really know. My brain is sad, and hurts.

Insert joke here relating to why [Joseph](https://www.thetorah.com/article/joseph-and-the-famine-the-storys-origins-in-egyptian-history) was paid the big bucks by Pharoah to manage Egypt's agricultural sector mid-famine.

And lo and behold, here's the deeply flawed essay:

## The Cultivation Conundrum (or Planting Problem)

Discussing investments the other day with a friend of mine, we dove into the concept of a liquid-to-illiquid asset ratio. That is, the breakdown of an individual’s material wealth into buckets of items which can, or can not, be transferred easily into cash. At a glance, it appeared that a large portion of the US population’s wealth is tied up in illiquid assets, such as homes, cars, and 401ks. Why is this interesting? Because this ratio influences the way we utilize our more liquid assets. If you had 90% of your wealth locked away in a vault, how would you spend and invest the remaining 10%? How would your behavior differ if you had 50% of your wealth tied up? Behavioral economists would likely say that this ratio impacts your risk appetite when investing, which [matters](https://www.nngroup.com/articles/prospect-theory/).

Illiquid assets aren’t just a modern phenomena either. Humans have been navigating complicated asset arrangements, perhaps unwittingly, for the past ~12,000 years. Let me explain. With the dawn of the Neolithic Revolution in 10,000 BCE, humanity first reaped (pun intended) the rewards of new agricultural methods. Grains such as wheat, barley, and rice grew from our fields, and in turn became the lifeblood of the civilizations which they lifted out of nomadic obscurity. As a quasi-fungible asset, grains harvested could be planted, stored, and even traded for other goods and services. These staple crops, being significant measures of societal wealth, dictated the livelihoods of the populations which grew them. Complicating matters though was that these assets couldn’t simply be held in perpetuity; grain decays after all. Similar to the modern man who locks his money away in illiquid investments, the ancient man stuffed his grain into the fertile ground, with hopes that his profit would eventually rise to see the light of day. Year after year, extensive deliberations over asset allocation were made. Plant too much, and your people’s fate becomes tightly tied to the subsequent harvest. Plant too little, and the grain reaped may not offset the grain consumed and decayed over the course of the year, resulting in a vicious cycle.

With a simplified model, we can attempt to better understand the circumstances faced by our ancestors as they made these decisions. Let’s start by breaking down grain usage into two buckets – storage and cultivation. Grain stored decays at some rate, while grain cultivated is either multiplied on good harvests, or decimated on bad ones.

![store and cultivate fns]({{site.baseurl}}/assets/img/store_and_cultivate_fns.png){:class="img-responsive" zoom="20%"}

With one unit of time per harvest, we can define a generalized recurrence relation:

![simple recurrence fn]({{site.baseurl}}/assets/img/simple_recurrence_fn.png){:class="img-responsive" zoom="20%"}

Accounting for annual societal consumption of grain, this becomes:

![recurrence fn with consumption]({{site.baseurl}}/assets/img/recurrence_fn_w_consump.png){:class="img-responsive" zoom="20%"}

Of course, there’s also a constraint in the maximum amount of grain which a society can own at any point in time. This is defined by the cumulative total of grain which could be both planted and stored in any given planting cycle. Applying this constraint, we get:

![max grain constraint]({{site.baseurl}}/assets/img/max_grain_constraint.png){:class="img-responsive" zoom="20%"}

For a rational actor seeking grain (read “wealth”) maximization, finding an optimal strategy is fairly simple. Whichever grain utilization function, either store or cultivate, has the greater EV (“Expected Value”) should be the function used in full. Calculating these EVs, we get:

![expected value]({{site.baseurl}}/assets/img/expected_value.png){:class="img-responsive" zoom="5%"}

If `P(Y=1)m <= 1`, then an optimal strategy would be to store all of the grain, otherwise the grain should be used fully for cultivation. Of course, losing the entirety of one’s grain in a poor harvest would be painful. But, it wouldn’t necessarily be a death sentence either. Individuals engaged in larger communities could have had the fallback option of trading with neighbors when times were rough.

While large harvests, and even larger stockpiles, likely excited our ancestors, an even more compelling communal objective would have been the maximization of their likelihood of survival as a group. Formally speaking, survival entails that an isolated society continually maintain an amount of grain above zero. We can call this the “survival clause”:

![survival clause]({{site.baseurl}}/assets/img/survival_clause.png){:class="img-responsive" zoom="5%"}

With longevity as the imperative, what would our optimal strategy become? 

After a bit of research, here’s the Cultivation Conundrum (or Planting Problem) which may have been experienced by ancient wheat farmers in the Eastern Mediterranean (see Appendix for variables):

![cult conun with vars]({{site.baseurl}}/assets/img/cult_conun_w_vars.png){:class="img-responsive" zoom="20%"}

Simulating this model over the full spectrum of possible strategies, we can find our optimal. The simulations constructed take in a starting amount of grain and a longevity goal, and run 100k tests on a given strategy before determining it’s survival rate. It should be noted that the starting grain amount (g_0) is represented as a factor of C. Here are the results of one simulation:

![graph1]({{site.baseurl}}/assets/img/cult_conun_graph1.png){:class="img-responsive" zoom="20%"}

Our optimal is somewhat of a plateau, with strategies `0.2 <= p_n <= 0.4` yielding very similar results and a fairly steep drop-off of survival rates outside of that zone. Testing out different g_0 values, we can see similar forms emerging. 

![graph2]({{site.baseurl}}/assets/img/cult_conun_graph2.png){:class="img-responsive" zoom="20%"}
![graph3]({{site.baseurl}}/assets/img/cult_conun_graph3.png){:class="img-responsive" zoom="20%"}
![graph4]({{site.baseurl}}/assets/img/cult_conun_graph4.png){:class="img-responsive" zoom="20%"}
![graph5]({{site.baseurl}}/assets/img/cult_conun_graph5.png){:class="img-responsive" zoom="20%"}

As the starting grain supply increases, our optimal plateau shifts further to the left with an ever increasing survival rate. The width of these plateaus remain relatively thin though, at around 10-20%.

If this model is to be trusted as an approximation of reality, then the ancients had a serious problem on their hands. Since `P(Y=1)m > 1`, an individual seeking more grain (read “wealth”) would have been incentivized to plant all of their grain. As we can see above though, communities prioritizing sustained survival would have needed much lower planting rates. This wide gulf in optimal behavior manifests a textbook [coordination problem](https://conceptually.org/concepts/coordination-problems), where leaving everyone to act on their own self-interest produces a worse outcome for all.  Problems like these make strong cases for centralized and cooperative decision making. That is, communities coming together to determine their own collective course of action.

Historically speaking, plenty of societies have undermined individual agricultural interests. May this have been for a collective good? Ancient Egypt had intensely socialized agricultural production, with government bureaucrats directing farmers/serfs on what quantities of which crops to plant where. And when the yield came, what price it should even be sold at. In a different form, we can see the Israelis in the Old Testament exhibit similarly communal behavior. The second chapter in what amounts to be their very first codified book of law, Leviticus, is dedicated to describing grain offerings. Later in Leviticus it is ordered that Israelis, “bring the first sheaf of your harvest to the priest...”, and seven weeks after that, “present a new grain offering...” (Leviticus 23) Probably the most staggering of anti-competitive, communal decisions which the Ancient Israelis made though was the “sabbatical” year they gave their farmland. Once every seven years, they decided to give their lands a complete rest (Leviticus 25). For the individual land owner, it must’ve been tempting to plant and disrupt these quiet, but lucrative, grain markets. Unified though as a community, these policies likely enhanced yield consistency for all.

Did the rise of agriculture actually bring about an existential conflict of interest between individuals and their society? Could this have sparked the creation of complex states capable of centralized planning? Of course, any of this is hard to tell for certain, but we can speculate.

# References

[1] : “Grain Storage Techniques: Evolution and Trends in Developing Countries.” Food and Agriculture Organization of the United Nations, 1994, www.fao.org/3/t1838e/T1838E06.htm#Improvement to storage on the farm.

[2] Klein, Robert. “Determining the Seeding Rate for Winter Wheat.” CROPWATCH, Nebraska Institute of Agriculture and Natural Resources, 4 Dec. 2018, cropwatch.unl.edu/determining-seeding-rate-your-winter-wheat.

[3] Huang, Ming-Li. “Water and Nutrient Use Efficiency in Diploid, Tetraploid and Hexaploid Wheats.” ResearchGate, 2007, www.researchgate.net/figure/Biomass-grain-yield-g-pot-and-harvest-index-of-different-wheat-genotypes-under_tbl1_228398961.

[4] Cook, Benjamin I., et al. “Spatiotemporal Drought Variability in the Mediterranean over the Last 900 Years.” Journal of Geophysical Research: Atmospheres, John Wiley & Sons, Ltd, 4 Mar. 2016, agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2015JD023929.

[5] Paulette, Tate. Domination and Resilience in Bronze Age Mesopotamia. University of Washington, faculty.washington.edu/stevehar/Paulette2012.pdf.

[6] “List of Famines.” Wikipedia, Wikimedia Foundation, 15 June 2019, en.wikipedia.org/wiki/List_of_famines.

## Appendix

# Explanation of Variable Inputs to the Eastern Mediterranean Cultivation Conundrum

# Base Cultivation Conundrum Model:

![base cult conun model]({{site.baseurl}}/assets/img/base_cult_conun_model.png){:class="img-responsive" zoom="20%"}

# Variables:

`r = 0.05` ; rate of decay for traditionally stored grains in tropical countries [1]

`m = 8.8` ; the most time-consuming of parameters to deduce – 
(seed yield/ plant of Triticum vulgare) * (typical germination rate of Triticum vulgare) * (grain yield ratio of Triticum boeoticum : Triticum vulgare) = (110 seeds/plant [2]) * (.8 plants/seed [2]) * (.1 seeds/ seed [3]) ;  Note: Triticum boeoticum is an ancient wheat known as “einkorn”, and Triticum vulgare is modern common wheat

`P(Y=1) = 0.75` ; conservatively high estimate given two facts: over the past ~1,000 years, 29% of the Mediterranean basin experienced drought any given year [4], and 36% of years produce no harvest in regions of Northern Mesopotamia [5]

`g_max = 8C` ; conservatively high as well, given that droughts and famines lasting for shorter periods of time have caused significant damage to sophisticated societies [6]

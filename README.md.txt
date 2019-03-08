This is a model for my world of Wala. There are 23 economic blocks that may or may not be
countries.

*Dynamic Trade Costs*
This is the series of calculators that uses the Dijskra Algorithm to solve for the cheapest
cost of travel between any two countries. They are just my versions. They include
different ship and cart designs, distances (hex is about 2 days travel by horse flat-2-flat)
, tariffs, the markup that a medieval merchant would charge for the distance, and the final
cost in roughly capita/kiloton. In this case, capita is a measure of man-hours, except it is
1000men*year. It relates to the amount of workers required to maintain and operate the
trade route.

*Basket*
This is a complicated calculation that takes production barriers, populations, urbanization
rates, relative demand ratios, trade by tonnage, and trade by money. I did account for two
different technologies for hewing vs. sawmilling wood. However, I am not focussed on tech
right now.

I would recommend understanding my "test" series, because those are always my pilot programs
that I use to rigorize my ideas before I scale them up. Also, earlier versions of my model
show a simpler scaling, but later versions get complicated.

*Core of the Model*
The core idea is you have country A and country B. A can produce 2 beer units or 1 bread
unit, but not both. Country A demands 30% of the world's beer and 20% of the world's bread.
Country B can make 1 beer or 3 bread and demands 10% beer and 40% bread.

So, country A will make (0.3+0.1)*2/(2+1) = 0.27 beer units and (0.2+0.4)*1/(2+1) = 0.20
bread units.

Country B will make (0.3+0.1)*1/(1+3) = 0.10 beer units and (0.2+0.4)*3/(1+3) = 0.45
bread units.

In short, this should be a weighted average model, where the demanders offload their demand
proportional to the producer's production barrier. Technically, this is unoptimal. However,
I am assuming there is a fool who is making a dumb purchase and/or investment.

Later I added trade distances that push the demand closer to the demander. So, far away
suppliers don't supply the demander as much.

I added a demand power measure, by multiplying the production barrier terms. This demand
power is a measure of the wealth of a trade block. It increases the overall demand of a
block compared to other blocks.

I added rate locks. Such that if a country has x people, those people will need y bread. So,
this country doesn't need a relative demand for bread. It needs an absolute demand for
bread and will sacrifice all the other relative demand products, like bowstrings, for bread.
Dividing the absolute demand by the rate lock sets the ratio such that the block will demand
the absolute amount of bread or product.

I added supplies, which is the amount of that good in circulation. There is a number of
years every good has before it is consumed. Coins are not consumed, they are saved. There is
a money supply in every country of copper/silver/gold coins, but these supplies are cheated.
When I tried to create a reasonably large supply, I needed to expand the years in
circulation, because the countries that produced copper were overburdened. So, I had to
cheat and stretch the money supplies by about 86x, or the number of commodities in my model.
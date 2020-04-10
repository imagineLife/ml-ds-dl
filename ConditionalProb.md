# Conditional Probability
- if i have...
	- 2 events that depend on each other
- ...what is the probability that both will occur?
## Notation
P(B|A) = ( P(A,B) / P(A) )


**EX. SCENARIO && leading question**
- I'm a teacher
- I give my students two tests
- 60% of students pass BOTH tests
- 1st test is easier
	- 80% of students passed THAT first test
- ... **what percentage of students who passed the first test ALSO passed the second test?**
	- ... whats the probability of B given A
	- EQUATION in action
		- P(B|A) = ( P(A,B) / P(A) )
		- .6 / .8 = .75 
		- ... **75% of students who passed the first test passed the second test**


## In Python
**Mocking Data**
- 100K points
- representing people
- ages between 20s - 70s
- creating a CONDITIONAL PROBABILITY
	- older, the more likely you are to buy something
```
# genrate random numbers
from numpy import random

# assure consistent results every time this code is run
random.seed(0)

# python dict, object {age:people-count}
totals = {20:0, 30:0, 40:0, 50:0, 60:0, 70:0}

# python dict, object {age:purchase-count}
purchases = {20:0, 30:0, 40:0, 50:0, 60:0, 70:0}

#
totalPurchases = 0

# loop
for _ in range(100000):
	
	# random Decade
    ageDecade = random.choice([20, 30, 40, 50, 60, 70])
	
	# higher the age, higher the likelyhood
    purchaseProbability = float(ageDecade) / 100.0

	# add decade to totals obj
    totals[ageDecade] += 1

	# RANDOM purchase probability
    if (random.random() < purchaseProbability):
        totalPurchases += 1
        purchases[ageDecade] += 1
```

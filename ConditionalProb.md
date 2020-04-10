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
	
	# higher the age, higher the likelyhood, CONDITIONAL RELATIONSHIP
    purchaseProbability = float(ageDecade) / 100.0

	# add decade to totals obj
    totals[ageDecade] += 1

	# RANDOM purchase probability
    if (random.random() < purchaseProbability):
        totalPurchases += 1
        purchases[ageDecade] += 1
```
**Working with this data**
- E = purchasing
- F = age-range

**Probability of someone in their 30s buying something out of all the 30-yr-olds:**
- P(E/F) = float(purchases[30]) / float(totals[30])
- ```PEF = float(purchases[30]) / float(totals[30])```
	- returns .29929...

**Probability of someone BEING 30**:
- P(E) = float(totals[30]) / 100000.0
- ```PThirty = float(totals[30]) / 100000.0```
	- returns .1669...

**Probability of someone buying something, regardless of age**:
- P(E) = float(totals[totalPurchases]) / 100000.0
- ```PBought = float(totals[totalPurchases]) / 100000.0```
	- returns .45012...

## Finding 'dependencies' between variables in the data 
...is there a relationship between AGE && purchasing?
...If PBought and P[anyAge] were totally independant, PBought would be the same no matter the P[age]
- we can see some sort of potential dependency from the mis-matched values of PBought and pThirty

**Finding P(E,F) is being in 30's AND buying something, NOT restricted to JUST thirty-year-olds**
```
thirtyAndBoughtCount = float(purchases[30])
totalPeople = 100000.0
print("P(30's, Purchase)" + str(thirtyAndBoughtCount / totalPeople))
```
- returns .0748


## Proving non-relationships between vars
**Mock Data**
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
	
	# higher the age, higher the likelyhood, Non-CONDITIONAL-RELATIONSHIP
    purchaseProbability = .4

	# add decade to totals obj
    totals[ageDecade] += 1

	# RANDOM purchase probability
    if (random.random() < purchaseProbability):
        totalPurchases += 1
        purchases[ageDecade] += 1
```
**Get P(E|F), total Purchases divided by total number of 30-yr-olds**
```
PEF = float(purchases[30]) / float(totals[30])
print('P(purchase | 30s): ' + str(PEF))
```
- returns .398...

**Get P(E), probability of purchaing REGARDLESS of age**
```
PE = float(totalPurchases) / 100000.0
print("P(Purchase):" + str(PE))
```
- returns .4003...

These numbers are close, showing very little connection btwn age && probability

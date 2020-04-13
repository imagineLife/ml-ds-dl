# Baye's Theorum
THE KEY INSIGHT
- The probability of something that depends on B 
	- depends very much on the base probability of B AND A

2 vars, A && B
The Probability of A Given B, is...
- the probability of A 
- TIMES
- the probability of B given A
- OVER 
- the probability of B

P(A | B) =  ( P(A) P(B|A) ) / P(B)

Example
- a drug test
	- can produce a positive result, LEADING to a potential positive USER result
	- BUT 
	- testing positive doesn't explicitly mean that the person is a USER

BAYE'S Theorem to the rescue!!
Say
- a drug test claims '99% accuracy' in users of a drug, drugZ
- .3% of the population ACTUALLY uses drugZ
- the 99%, here, isn't high-enough to be helpful, SAYS BAYE'S 
- A, is a user of the drug
- B, tested positively for the drug

THEOREM in-process
	- probOfUsingDrug, Given that you tested positively...
		- probabilityOfTestingPositively = ( .99 * .003 ) + ( .01 * .997 )...
			- probability of testing positive if you DO use
			- PLUS
			- probability of testing positive if you DON'T use
			- comes out to 1.3%, or .013
		- probBeingAUser = P(A) = .003 (.03%)
		- probTestingPositiveAsAUser = P(B | A) = .003 * .99 (.03% * 99%) = .00397


Another way

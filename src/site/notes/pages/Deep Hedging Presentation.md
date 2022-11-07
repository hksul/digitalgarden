---
{"dg-publish":true,"permalink":"/pages/deep-hedging-presentation/"}
---



https://arxiv.org/pdf/2103.16409.pdf


---
 
 

 


## Deep Hedging
- Greek Hedging 
	- Based on a theoretical model
- Statistical Hedging
	- Data driven risk management
	- But still relies on modes for pricing
- Deep Hedging
	- AI driven reinforcement learning 
	- For risk management and derivatives pricing

--
### Hedging through Greeks
- Delta Hedging 
	- Partial derivative of the value of a transaction with respect to the underlying asset 
	- $$\Delta = \frac{\partial C}{\partial S}$$
- Trader's Actions
	- Traders typically try to maintain delta-neutral
	- Ex) Delta hedging requires shares to be purchased as soon as  option is sold.
--
### Issue with Delta Hedging
- Delta changes over time...
	- Trader’s position must be rebalanced 
	- If there are no transaction costs/friction
		- Optimal to rebalance continuously 
	- In practice, transaction costs / frictions exists
- Delta hedging is no longer optimal. 
	- Optimal for a trader to be underhedged relative to delta (purchase fewer shares)
	- Ex) It may be optimal not to hedge if trading costs are too high


--

### Deep Hedging
- Reinforcement learning for Hedging
	- •Take Trading Cost into Account in Hedging
- Objective function
	- Ex) Expected cost of hedging plus a constant times the standard deviation of the cost
- Other use cases
	- Hedging exposure to volatility.
	- Exotics (Ex: barrier options) 
		- ... are difficult to hedge using the underlying asset 
		- Even when trading costs are negligible
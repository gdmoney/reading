## Algorithms to Live By
-- *Brian Christian and Tom Griffiths*


### Optimal Stopping
- 2 ways to fail: stopping early or stopping late
- Secretary Problem
- 37% Rule - can be applied to applicants or to time
- no information > **Look-Then-Leap Rule**
- full information > **Threshold Rule** (58% success rate)
- **Burglar Problem**
- the flow of time turns all decision-making onto optimal-stopping problems


### Explore/Exploit
- how our goals should change as we age
- **Multi-armed Bandit Problem**
- **Win-Stay, Lose-Shift** algorithm
- discounting - valuing the present more highly than the future
- **Gittins Index**
- **Upper Confidence Bound** algorithm - optimism in the face of uncertainty
- time availability should drive the strategy


### Sorting
- key to the human experience of information
- sort vs search
- `Big-O` notation - inexact measure of algorithmic worst-case performance
- constant `O(1)`, linear `O(n)`, quadratic `O(n^2)`, exponential `O(2^n)`, factorial `O(n!)`
- algorithms: Bubble, Insertion, Mergesort, Bucket, Comparison Counting
- err on the side of messiness


### Caching
- what to keep and how to arrange it
- time vs space (small and fast or big and slow)
- cache eviction
- **LRU** algorithm - evicting the item that's gone the longest untouched
- **temporal locality** - if a program has called for a particular piece of information once, it's likely to do so again in the near future
- best guide to the future is a mirror image of the past
- milti-level memory hierarchy - from smallest and fastest to largest and slowest


### Scheduling
- speed vs accuracy (slow and accurate/robust or fast and error prone/brittle)
- maximize overlap
- debt avalanche (amount) vs debt snowball (quantity)
- **precedence constraint** - a certain task can't be started until another one is finished
- **Weighted Shortest Processing Time** - best general purpose strategy
- **context switching** - overhead of wasted time when a processor shifts its attention away from a given program; metawork
- **thrashing** - a system running full-tilt, grinds to a halt, accomplishing nothing because it's entirely preoccupied with metawork
- **interrupt coalescing** - interrupt moderation, to minimize context switching
- responsiveness vs throughput (cost is delay) - how quickly you can respond to things, and how much you can get done overall


### Bayes's Rule
- predicting the future
- **Laplace's Law** - for any possible drawing of `W` winning tickets in `N` attempts, the expectation is: `W+1/N+2`
- **Bayes's Rule** - describes the probability of an event, based on prior knowledge of conditions that might be related to the event
- **Copernican Principle** - if we want to predict how long something will last, and have no other knowledge about it whatsoever, the best guess we can make is that it will continue just as long as it's gone on so far
- **Natural (bell curve) distribution** - events are surprising when they're early, since we expected them to reach the average - but not when they're late
- **Power-law distribution** - the longer something has gone on, the longer we expect it to continue going on
- **Erlang distribution** - events are never any more or less surprising no matter when they occur; memoryless distribution
- **Marshmallow Test**: willpower or expectations (Normal vs Power-law)


### Overfitting
- how many factors to consider when making a decision
- more complex models are often worse due to noise
- **Cross-Validation** - assessing not only how well a model fits the data it's given, but how well it generalizes to data it hasn't seen
- **Regulatization** - using constraints that penalize models for their complexity
- **Early Stopping** - full data and low uncertainty > stop late; limited data and high uncertainty > stop early


### Relaxation
- solve easier version of a problem first
- **Constrained Optimization** problem - how to find the single best arrangement of a set of variables, given particular rules and a score-keeping measure (the traveling salesman problem)
- **intractable problems** - problems that can't be solve in polynomial time: `O(n^2)`, `O(n^3)`, `O(n^n)`
- **Discrete Optimization** - searching for an optimal solution in a finite or countably infinite set of potential solutions
- **Constraint Relaxation** - removing some constraints altogether and makes progress on a looser form of the problem
- **Continuous Relaxation** - turns discrete or binary choices into continua
- **Lagrangian Relaxation** - turns impossibilities into mere penalties


### Randomness
- making use of chance can be a deliberate and effective part of aproaching the hardest sets of problems
- randomized vs deterministic algorithms
- **Monte Carlo Method** - replacing exhaustive probability calculations with sample simulations
- **time and space** vs **certainty**


### Networking
- protocol - a shared convention of procedures and expectations
- how do you know when your messages are getting through?
- **Two Generals Problem**
- **Exponential Backoff** algorithm - increasing the average delay after every successive failure before trying to transmit again
- **AIMD** - algorithms used by TCP for flow control and congestion avoidance


### Game Theory
- study of theoreticaly ideal strategies for games and scenario sof cooperation and competition
- **Algorithmic Game Theory** - how people come up with strategies for games
- **Halting Problem** - a computer program can never tell you for sure whether another program might end up calculating forever without end - except by simulating the operation of that program
- **Recursion** - any time a system simulates the workings of something as complex as itself, it finds its resources totally maxed out, more or less by definition
- **Equilibrium** - a set of strategies that both players can follow such that neither player would want to change their own play, given the play of their opponent
- **Nash Equilibrium** - prediction of the stable long-term outcome of any set of rules or incentives
- **Prisoner's Dilemma** - stable doesn't make it good; equilibrium strategy does not necessarily lead to the best outcome for the players
- **Dominant Strategy** - the best response to all of your opponent's possible strategies - avoids recursion altogether
- **Price of Anarchy** - measures the gap between cooperation and competition
- **Tragedy of the Commons** - a situation in a shared-resource system where individual users, acting independently according to their own self-interest, behave contrary to the common good of all users by depleting or spoiling the shared resource through their collective action
- **Mechanism Design** (aka reverse game theory) - takes an objectives-first approach to designing economic mechanisms or incentives, toward desired objectives, in strategic settings, where players act rationally
- adopting a strategy that doesn't require recursion (anticipating, predicting, reading into, changing course) is optimal and easy


### Conclusion
- any dynamic system subject to the constraints of space and time is up against a core set of fundamental and unavoidable problems
- if you follow the best possible process, then you've done all you can, and you shouldn't blame yourself it things don't go your way
- **Computational Kindness** - behavior and design principle
- computation is inefficient: the underlying directive of any good algorithm is to minimize the labor of thought
- by not stating our preferences, we (1) pass the cognitive buck back and (2) invites others to simulate your thinking - recursion
- algorithms are all about doing what makes the most sense in the least amount of time
- effective algorithms make assumptions, prefer simpler solutions, trade off error against delay, and take chances
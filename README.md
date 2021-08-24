# Authors

Chapman University, CS 596 - Computational Economics II

James, K. (2019). Estimating Auction Equilibria using Individual Evolutionary Learning. Chapman University.

Steve Vu

# 1. Introduction

The project aims at finding optimal strategies of firms competing for rights of owning goldmines in several auctions, each for a different goldmine. The value of a goldmine is the same no matter who ends up owning the mine.

In each auction, price starts at a low level, ascends up, and ends when only one firm is remaining. While a firm has its own valuation, it is able to observe others' decisions and update/revise its strategy before entering into next rounds.

# 2. Common Value Auctions For Goldmines

In this version, I apply the general framework of Markov Chain to learning economic decision making of two firms who participating into auction of goldmines.

At the beginning of an auction, firms know that the true VALUE of any particular goldmine is drawn uniformly from the interval [10, 100] with a step size of 5. The value of one mine does not affect the value of another mine.

Each firm can purchase up to 5 signals about how much gold is in the mine. Each signal is drawn randomly from [VALUE - 25, VALUE + 25]. No one will see others' signals as that is private information. However, everyone will be able to see how many signals other bidders purchased once the auction starts.

The auction price is set well below the true value of the goldmine and gradually increase by a step size of 5. At any point, a firm can decide on staying in or leaving the auction by calculating actions' expected values based on Bayesian estimate of true value conditional on the current state.

If one firm has left the auction, the auction stops. The firm who is still in the auction becomes the owner of the goldmine and receives the VALUE. Otherwise, the auction will transit to next state where the price goes up by a step size.
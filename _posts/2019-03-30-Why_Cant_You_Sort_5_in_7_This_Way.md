---
layout: post
author: Anastasia Makarevich
title: "How not to sort 5 stones in 7 steps"
date: 2019-03-30
---

This problem was also a part of my review of the computation theory. I had to make a proof and enjoed it so much, 
that I decided to share.

<h2>Introduction</h2>

The goal is to sort 5 stones from lighest to heaviest. The lower bound for sorting 5 stones is 7. In order to achieve it, we must start with making two pairwise comparisons: e.g. 1st with 2d,
3rd with 4th. The last stone will be left off. The question is - is it really the neccessary step? Maybe we could still sort 5 stones
in 7 steps if we don't make these pairs? Instead, what if we compare 1st and 2d and then compare 3rd to 1st? How to prove, that
it's impossible to sort the stones in 7 steps in this scenario? 


<h2>Proof</h2> 

In the beginning we 120 possible stone ordering (5!). The lower bound for that is 7. In the suggested scenario, after performing
the first two steps, we are left with 40 orderings. Here is why. First, consider that we've compared the new stone only with one of the
two in the pair, so in the worst case it's lighter than the heavier one, but we don't know how it compares to the lighter one. So there 
are two branches and after computing all the orderings, we should multiply it by 2. Now, in one of the branches we can assume
that these three are ordered. Let's call them A B C. The remaining stones are D and E. 
Then the following orderings are possible: 

1) ABC act together as one, then we have 3! ways to order ABC, D and E. -> total 6 orderings 
2) There is exactly one stone inside ABC: AxBC or ABxC, where x is in {D,E}. And there are two ways to order them. So total: 2*2*2 = 8
3) There is exactly one stone between A and B and B and C: AxBxC, x in {D,E}. It gives us 2 combinations
4) There are exactly two stones inside ABC: AxyBC or ABxyC, x,y in {D,E}. 2 ways to sort xy, 2 ways to place xy, total 4

Summing up from 1) to 4): 6+8+2+4 = 20. And we also have to multiply by 2 for two branches we mentioned in the beginning. Total - 40 
ways to order our stones after the second step. 40 is between 2^5 and 2^6. So the lower bound for 40 combinations is 6 in addition
to these two steps. So, **at least** 8 steps are required to sort 5 stones in this scenario, and it's no possible to do it in 7. 

QED.


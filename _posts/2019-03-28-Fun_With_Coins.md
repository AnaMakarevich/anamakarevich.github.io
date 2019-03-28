---
layout: post
author: Anastasia Makarevich
title: "Fun with Coins (Optimal Solution)"
date: 2019-03-28
---

Today I wanted to share an intersting puzzle, which is not directly related to computer or data science. 
It's more of a brain burner, but I enjoyd solving it. 

<h2>Problem:</h2>
We have 12 golden coins and 12 silver coins. One of them is fake and we don't even know if it's silver or golden. Moreover, we don't know what is heavier - golden coins or silver coins. But we have scales that can tell us if something is heavier or not. 
Question: what is the minimal number of operations required to find the fake? 

Answer: 3

Wait, but how? 

<h2>Explanation:</h2>

Note: I will be very detailed, because I remember how annoying it is when someone skips the steps!

<h3>Step 1:</h3>

Split all the coins into three groups: 

A: (4 golden, 4 silver), B: (4 golden, 4 silver), C: (4 golden, 4 silver). 

Coompare A and B. Now consider three cases: 

1) A < B -> the fake is either in golden coins in A or in silver coins in B
2) A > B -> the fake is either in golden coins in B or in silver coins in A
3) A = B -> the fake is in C

In cases 1) and 2) we would want to select all suspiction coins - 4 golden and 4 silver from different groups: 
in case 1) we will take 4 golden from A and 4 silver from B; in case 2) we will take 4 golden from B and 4 silver from A. 
In case 3) we already have the pile of 4 golden and 4 silver. So in all 3 cases we reduced the problem to the problem of finding a fake in (4 golden and 4 silver coins) and used only 1 step so far!

<h3>Step 2:</h3>

Split the remaining coins into the following groups: 

A: (2 golden, 1 silver), B: (2 golden, 1 silver), C: (2 silver) 

Compare A and B. Now consider three cases: 

1) A < B -> the fake is either in golden coins in A or in silver coin in B
2) A > B -> the fake is either in golden coins in B or in silver coin in A
3) A = B -> the fake is in C

In case 1 and 2 we again select all the suspictios coins - 2 golden and 1 silver from different groups: 
in case 1) two golden from A and one silver from B, in case 2) two golden from B and one silver from A. In case 3) we're left with just two coins. 


<h3>Step 3:</h3>

For cases 1) and 2) from Step 2 we only need to compare the two golden coins. If one of them is lighter, then it's a fake. 
If they have the same weight, then the fake is the silver one.
For case 3) we only need to compare the two silver coins.

That's it! 


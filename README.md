
# Permutations and Factorials

## Introduction

In the previous lab, you defined a few sample spaces by counting the total number of possible outcomes. This is not very practical when sample spaces grow. In this lab, you'll be introduced to *permutations*, which will provide a structured way to help you define sample space sizes!

## Objectives

You will be able to: 

* Describe how factorials are related to permutations
* Mathematically derive how many permutations there are for large sets
* Calculate permutations of a subset
* Calculate permutations with repetition and replacement

## Defining the Sample Space by Counting

Let's consider the following example.

The Beyoncé tribute band "The Single Ladies" is playing a free mini gig in your local park next week. They have selected three all-time classics: "Drunk in Love", "Crazy in Love" and "Formation", but still have to decide the order they will play the songs in. Knowing this, how many playlists are possible?

It is easy and fairly quick to write down possible orders here:

"Drunk in Love", "Crazy in Love", "Formation"

"Drunk in Love", "Formation", "Crazy in Love"

"Crazy in Love", "Drunk in Love", "Formation"

"Crazy in Love", "Formation", "Drunk in Love" 

"Formation", "Drunk in Love", "Crazy in Love"

"Formation", "Crazy in Love", "Drunk in Love"

That's it! When we count the possible outcomes, we get to 6 elements in the sample set. Now what if "The Single Ladies" plays a setlist of 4 songs? or 5? That's where the notion of *permutations* comes in handy.


## Permutations

The problem setting, in general, is that there are  <img src="https://render.githubusercontent.com/render/math?math=n"> objects and we want to know how many *permutations* are possible.

This is a way how you can tackle this. You're the lead singer and have to decide which song to play first. You have 3 songs to choose from, so 3 ways of choosing a first song. Then, you move on to the second song. You've chosen the first one, so you have 2 songs to choose from now, etc. Mathematically, this boils down to:

  \# Beyoncé permutations<img src="https://render.githubusercontent.com/render/math?math== 3*2*1 = 3! = 6"> 

Generalizing this to  <img src="https://render.githubusercontent.com/render/math?math=n"> , this means that the number of permutations with  <img src="https://render.githubusercontent.com/render/math?math=n"> distinct objects is  <img src="https://render.githubusercontent.com/render/math?math=n!"> , or the factorial of  <img src="https://render.githubusercontent.com/render/math?math=n"> .

## Permutations of a Subset

Now, let's consider another example. "The Single Ladies" are still playing a concert at central park, but they disagree on the final three songs that they will play. They only get a 12 min gig slot, so they really can't play more than 3, yet they have a shortlist of 8 they need to pick from. How many final song selections are possible given this info? As for the first example, the order of the songs played is still important.

When the band members decide on the first song, they have 8 possible songs to choose from. When choosing the second song, they have 7 to choose from. Then for the third song, they have 6 left.

  \# Beyoncé k-permutations<img src="https://render.githubusercontent.com/render/math?math== 8*7*6 = 336"> 

formalizing this, the question is how many ways we can select  <img src="https://render.githubusercontent.com/render/math?math=k"> elements out of a pool of  <img src="https://render.githubusercontent.com/render/math?math=n"> objects. The answer is 

 <img src="https://render.githubusercontent.com/render/math?math=n*(n-1)*...*(n-k%2b1)"> or in other words,  <img src="https://render.githubusercontent.com/render/math?math=P_{k}^{n}= \dfrac{n!}{(n-k)!}"> 

This is known as a  <img src="https://render.githubusercontent.com/render/math?math=k"> -permutation of  <img src="https://render.githubusercontent.com/render/math?math=n"> .

The idea is here that we only "care" about the order of the first  <img src="https://render.githubusercontent.com/render/math?math=k"> objects. The order of the other  <img src="https://render.githubusercontent.com/render/math?math=(n-k)"> objects doesn't matter, hence they're left out of the equation.

## Permutations with Replacement

When talking about setlists, it makes total sense to assume that songs will not be played twice. This is not always how it works though. Imagine a bag with three marbles in it: a green one, a red one, and a blue one. Now we'll draw marbles three times in a row, but each time, we'll write down the marble color and *put it back in the bag* before drawing again.

Now the number of possible outcomes is  <img src="https://render.githubusercontent.com/render/math?math=3 * 3 * 3"> .

Generalizing this to  <img src="https://render.githubusercontent.com/render/math?math=n"> , this means that the number of permutations with replacement when having  <img src="https://render.githubusercontent.com/render/math?math=n"> distinct objects is equal to  <img src="https://render.githubusercontent.com/render/math?math=n^j"> where  <img src="https://render.githubusercontent.com/render/math?math=j"> is the number of "draws".

## Permutations with Repetition

When using permutations, some elements may be *repeated*.

A classic example is using permutations on words. Let's say you have the letters of the word "TENNESSEE". How many different words can you create using these letters?

Simply saying that there are 9 letters so the answer is  <img src="https://render.githubusercontent.com/render/math?math=9!"> does not give you the correct answer. Looking at the word TENNESSEE by itself, you can swap the 3rd and the 4th letter and have the same word. So the total number is less than  <img src="https://render.githubusercontent.com/render/math?math=9!"> .

The solution is to divide  <img src="https://render.githubusercontent.com/render/math?math=9!"> by the factorials for each letter that is repeated!

The answer here is then (9 letters, 4 x E, 2 x N, 2 x S)

 <img src="https://render.githubusercontent.com/render/math?math=\dfrac{9!}{4!2!2!} = 3780"> 

The general formula can be written as:

 <img src="https://render.githubusercontent.com/render/math?math=\dfrac{n!}{n_1!n_2!\ldots n_k!}"> 

where  <img src="https://render.githubusercontent.com/render/math?math=n_j"> stands for identical objects of type  <img src="https://render.githubusercontent.com/render/math?math=j"> (the distinct letters in our TENNESSEE example). 

## Level-Up: Factorials and Recursion 

At the start of this lesson, when discussing the number of possible permutations we can obtain for n distinct objects, we mentioned the concept of the factorial of n, denoted by  <img src="https://render.githubusercontent.com/render/math?math=n!"> . 

In the example presented to you, we wanted to count all possible ways in which three different Beyoncé songs could be played by the Beyoncé tribute band "The Single Ladies". There were 3 possible ways of choosing a first song, 2 possible ways of choosing a second song, and only 1 way of choosing a third and final song, for  <img src="https://render.githubusercontent.com/render/math?math=3 * 2 *1 = 6"> different ways in which the three different songs could be played. This number, 6, is equal to the factorial of 3,  <img src="https://render.githubusercontent.com/render/math?math=3!"> , the number of permutations of 3 distinct objects. 

Here,  <img src="https://render.githubusercontent.com/render/math?math=3! = (3 * 2 * 1) = 6"> . Notice that this is the same as writing  <img src="https://render.githubusercontent.com/render/math?math=3 * 2! = 3 * (2 * 1)"> and  <img src="https://render.githubusercontent.com/render/math?math=3 * 2 * 1! = 3 * 2 * (1)"> . (By definition, the factorial of 1,  <img src="https://render.githubusercontent.com/render/math?math=1!"> , is equal to 1. The factorial of 0,  <img src="https://render.githubusercontent.com/render/math?math=0!"> is also defined to be equal to 1.)

We can generalize this to the case of computing the factorial of an integer n,  <img src="https://render.githubusercontent.com/render/math?math=n!"> . The factorial of n,  <img src="https://render.githubusercontent.com/render/math?math=n!"> , can be written as  <img src="https://render.githubusercontent.com/render/math?math=n * (n-1)!"> , which itself can be written as  <img src="https://render.githubusercontent.com/render/math?math=n * (n-1) * (n-2)!"> . That is, we can define the factorial of n in terms of the product of  <img src="https://render.githubusercontent.com/render/math?math=n"> and the factorial of  <img src="https://render.githubusercontent.com/render/math?math=(n-1)"> , and the factorial  <img src="https://render.githubusercontent.com/render/math?math=(n-1)"> can be defined in terms of the product of  <img src="https://render.githubusercontent.com/render/math?math=(n-1)"> and the factorial of  <img src="https://render.githubusercontent.com/render/math?math=(n-2)"> , and so on and so forth, as seen in the equation below, until we get to  <img src="https://render.githubusercontent.com/render/math?math=1!"> , which is defined to be equal to 1: 

 <img src="https://render.githubusercontent.com/render/math?math=n! = n * (n-1)! = n * (n-1) * (n-2)! = ... = n * (n-1) * (n-2) * \ldots * 2! = n* (n-1) * (n-2) * \ldots * 2 * 1! "> 

### Recursion 
When we define a function in terms of itself, in this case, the factorial of n in terms of the factorial of (n-1), we are using **recursion**.  Recursive functions are functions that can call themselves in order to loop until a condition is met. In the next lab, you'll get a glimpse on how to write a recursive function in Python, but in the Appendix to this Module, we go over recursive functions in Python in much more detail.

## Summary

Now you're well on your way to calculate all sorts of permutations using factorials - both for understanding the sample space, subsets, etc! Let's move on for some practice!

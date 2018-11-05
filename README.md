
# Conditional Probability 

## Introduction

Conditional Probability is an important part of learning Statistics, which is mandatory in order to eventually understand and practice Machine Learning and Artificial Intelligence. In this lesson, we shall talk about conditional probability, how and when to use it and what benefits does it carry towards analytical tasks. We shall later see how this simple idea becomes a key component in most statistical machine learning algorithms. 

## Objectives:
You will be able to:

* Differentiate between independent and dependent random events 
* Understand and Explain the conditional probability - P(A∩B) = P(A|B) x P(B)
* Use the multiplication rule to find the probability of the intersection of two events
* Understand and describe some important theorems based on conditional probabilities

Let's quickly recap some of the basic ideas and terms which we shall later use in describing conditional probability use cases. 

## Events and Sample Space

An **Event** is the outcome of a random experiment e.g. watching heads on tossing of a coin, or getting 3 after a dice roll are events.  We need to specify the sample space and the events to compute event probability. An event may also be collection of different events grouped together e.g. rolling a dice 4 times. A **Sample space** is a collection of every single possible outcome in a trial. As the number of trials increases, our sample space contains all the achievable outcomes. For example, sample space for random throw of a die is {1,2,3,4,5,6}. One of these will undoubtedly happen in the event of throwing a die. The sample space depicts each one of the conceivable outcomes that can happen when the experiment is performed.

Events in a sample could be either **dependent** or **independent**. For two events P and Q, the chance that the occurring of event P doesn’t influence the occurring of event Q, these events are called as independent events. If the P occurrence of P is somehow dependent on occurrence of Q , P would be dependent on Q (think temporal data). 



### Independent Events

Consider following independent events 

* Getting heads after flipping a coin AND getting a 5 on throw of a fair die.
* Choosing a marble from a container AND getting heads in the flipping of a coin 

> Events A and B are __independent__ if $P(A \cap B) = P(A)P(B)$, and $P (A \cup B) = P(A) + P(B) -P(A \cap B)$  Remember that event A tells us nothing about event B.

![](ind1.jpg)
What about the case of three events A, B and C?

> Events A, B and C are __independent__ if 
>
> \begin\{align\}
>     P(A \cap B) &= P(A)P(B), ~~  P(A \cap C) = P(A)P(C), ~~ P(B \cap C) = P(B)P(C) \\\\
>     P(A \cap B \cap C) &= P(A)P(B)P(C)
> \end\{align\}
>
> So you need both _pair-wise independence and three-way independence_.




In contrast, events A and B are __disjoint__ if A occurring means that B cannot occur.

![](disj.jpg)




### Dependent Events 

When probability of occurrence of event A is somehow dependent or connected to occurrence of B, these become dependent events and this is where things start getting a bit more interesting. 

Consider this example, we characterize event A as getting a Red or Blue marble from the jug containing 3 red and 2 blue marbles (see image below).

<img src="marb.svg" width = 300>

So the probability of getting a blue marble would initially be 2/5 and getting a red marble would be 3/5.

<img src="cond3.gif" width = 300>
We at that point keep the marble out and after that take another marble from the jug. Here you can see that our second event is dependent on the outcome of first trial. IF we had a red marble in trial 1, the probability of getting a blue marble in trial 2 is 2/4. However, if we saw a blue marble in the first trial, the probability of seeing a blue in second trial becomes 1/4 etc. In simple terms, the probability of seeing an event B  in the second trial depends on the outcome A of the first trial , OR, P(B) is **conditional** on P(A).

A **tree diagram** can be used to explain this for all possible events.


<img src="tree.gif" width = 500>

## Conditional Probability 

> **Conditional Probability emerges in the examination of experiments where a result of a trial may influence the results of the upcoming trials.**

While calculating the probability of the second event (event B) given that the primary event (event A) has just happened, if there is a chance that A's outcome might have tempered with the sample space in some way, we can securely say that the probability of event B is reliant on the occurrence of event A.

Here are some more examples: 

* Drawing a 2nd Ace from a deck of cards given we got the initial Ace.
* Finding the probability of liking "Matrix" given the individual prefers science fiction.

If we consider event with P(A) as the probability of the event we are attempting to ascertain.
Event B is the condition that we know or the event that has happened.

We can compose the conditional probability (Probability of A **GIVEN** B) as :


<img src="cond2.png" width=300>


> **P(A|B)**, the probability of the taking place of event A **given** that B has just happened. 

<img src="cond4.png" width=300>

Here’s how to derive the conditional probability equation shown above from the multiplication rule:

Step 1: Write out the multiplication rule:
* **P(A and B) = P(B)*P(A|B)**

Step 2: Divide both sides of the equation by P(B):
* **P(A and B) / P(B) = P(B)*P(A|B) / P(B)**

Step 3: Cancel P(B) on the right side of the equation:
* **P(A and B) / P(B) = P(A|B)**

Step 4: Rewrite the equation:
* **P(A|B) = P(A and B) / P(B)**

And this is our conditional probability formula. Here we shall quickly summarize some variations and theorems which emerge from conditional probability that will be used for reference in later lessons. 

### Complement of an event

#### P(A')  - read as "Probability of the complement of Event A" or "Probability of A complement" or even "Probability of NOT A"

The complement is shown by a little mark after the letter such as A' (or sometimes A<sub>c</sub> or A<sup>c</sup>)

<img src="comp.png" width=500>


If for a dice roll, event A is seeing a 5 is P(A) = 1/6 , then P(A') is the probability of all other events in the sample space i.e. 1/6* 5 = 5/6

The two probabilities always add to 1
* P(A) + P(A') = 1

>  **Similarly P(A|B) + P(A'|B) = 1**


## Theorem 1 - Product Rule
The **Product rule** is useful when the conditional probability is easy to compute, but the probability of intersections of events are not. 

The intersection of events $A$ and $B$ can be given by

\begin{align}
    P(A \cap B) = P(B) P(A|B) = P(A) P(B|A)
\end{align}

Note that if $A$ and $B$ are independent, then conditioning on $B$ means nothing (and vice-versa) so $P(A|B) = P(A)$, and $P(A \cap B) = P(A) P(B)$ as we know already. 

## Theorem 2 - Chain Rule

The **chain rule** (also called the general product rule) permits the calculation of any member of the joint distribution of a set of random variables using only conditional probabilities. 

We can rearrange the formula for conditional probability to get the product rule:

>$P(A,B) = p(A|B) p(B)$

We can extend this for three variables:

>$P(A,B,C) = P(A| B,C) P(B,C) = P(A|B,C) P(B|C) P(C)$

and in general to n variables:

$$P(A1, A2, ..., An) = P(A1| A2, ..., An) P(A2| A3, ..., An) P(An-1|An) P(An)$$

In general we refer to this as the chain rule.

If on the other hand, if $C_1, C_2,...,C_m$ are disjoint events such that $C_1 \cup C_2 \cup ··· \cup  C_m = \Omega$ the probability of an arbitrary event can be expressed as:

\begin{align}
P(A) = P(A | C_1)P(C_1) + P(A | C_2)P(C_2) + ··· + P(A | C_m)P(C_m)
\end{align}

## Theorem 3 - Bayes rule

The **Bayes theorem**, which is the outcome of this section. Below is the formula that we will dig deeper into , in upcoming lessons.

\begin{align}
    P(A|B) = \frac{P(B|A)P(A)}{P(B)} ~~~~ \text{this follows from Theorem 1}
\end{align}

## Example : An Aspiring Data Scientist's Dilemma

Let's see a very simple use of conditional probability formula. A data scientist comes across following info-graphic:

<img src="mood.jpg" width=600>

Curious as data scientists are, he starts collecting data about weather conditions and his own mood. 

Consider the data in the following table, recorded over a month with 30 days by our data scientist. On each day he recorded whether it was sunny (S), or not (NS), and whether his mood was good (G), or not (NG).
<img src="x.png" width=300>

He wants to now know if his mood had anything to do with the weather on a particular day and how can he calculate the probability of having a good mood given the weather conditions. 


#### If he picked a day at random from the 30 days on record, what is the probability that he was in a good mood on that day, P(G)? 

* The sample space is the 30 days under discussion. 
* He was in a good mood on 9 + 6 = 15 of them so P(G) = 15/30 = 0.5

#### What is the probability that the day chosen was a Sunny day, P(S)?

* The sample space is still the 30 days under discussion. 
* It was sunny on 9 + 1 = 10 of them so P(S) = 10/30 ≈ 0.33

#### What is probability of having a good mood given its a sunny day  P(G|S) ?

* P(G|S) = P(G ∩ S) / P(S), hence we need to calculate P(G ∩ S) first. 
* Here the sample space is still the 30 days
* G ∩ S consists of sunny days in which he is in a good mood and there were 9 of them. Hence P(G ∩ S) = 9/30
* Therefore P(G|S) = (9/30)/(10/30) = 0.9

The info-graphic had some truth in it indeed. There's a 90% chance that our curious data scientist would be in good mood given its a sunny day.  The outcome of this experiment is comforting for our data scientist and calls this a successful experiment. Surfing the Internet, he comes across another piece of information, although not very scientific, raises his curiosity further. 

<img src="mood2.jpg" width=600>

What if .... ?

#### Now the data scientist wants to know weather his mood had any impact on the weather.  What is P(S|G)

P(S|G) = P(G ∩ S)/P(G) = (9/30)/(15/30) = .6

He finds that the probability is slightly higher than random chance. So in other words theres a 60% chance that it will be all nice and sunny if he is in a good mood. 

He also realizes that P(G|S) is not equal to P(S|G). So does this mean that weather has a higher impact over his mood than his mood has over the weather. 
<img src="whaaat.jpg" width=300>


Note that if we discover that P(A|B) is not equal to P(A), it  does not necessarily mean a cause effect relationship. In the example above, the weather and other such external conditions can have a positive effect on human mood and behavior, and this can be said with reference to literature. however it is unlikely that mood has any effect on weather, we do not have any scientific evidence to support this notion. 

Here we see that one can only go so far with Frequentist probabilities i.e. counting number of occurrences (frequencies) to work out the probability of an event. Frequentist methods do not allow the experimenter to augment his beliefs or other prior knowledge he has to an experimental design. So the experimenter would be mainly stuck with what he has observed. 

#### Say Hello to Reverend Thomas Bayes


<img src="bayes.jpg" width=300>

See the P(A) in the equation trying to calculate P(A|B), this is called "The Prior" and let's us add our prior knowledge to a learning process, and is the very foundation of predictive machine learning algorithms. 

Our data scientist realizes that he needs to learn a bit of Bayesian reasoning in order to get more meaningful results. And that is exactly what we will discuss in this section. First we need to cover a few topics to fully understand how this simple equation lets you do some serious predictive analysis. Let's do a few exercises next to get a good grip of conditional probability calculations.

## Additional Resources

You are strongly advised to visit following links to get an indpeth understanding with examples and proofs for formulas highlighted in this lesson. 

[Conditional probability, Independence and Bayes rule](http://faculty.arts.ubc.ca/vmarmer/econ327/327_02_cond_probability.pdf) - A deeper mathematical explanation around Independence and theorems we have seen above (and some we shall cover in upcoming lessons)

[Tree Diagrams](https://www.mathsisfun.com/data/probability-tree-diagrams.html) - Drawing Tree diagrams to calculate conditional probability

[Conditional Probability, Examples and simple exercises](https://www.mathgoodies.com/lessons/vol6/conditional) - Practice around probability calculations

[Conditional probability: A visual explanation](http://setosa.io/conditional/) - A great little interactive animation to explain how conditional probability works

## Summary 

In this lesson , we talked about the conditional probabilities in case we have dependent events in our sample space. We looked at the formula to calculate such probabilities with a brief proof. We also looked at an example to see this concept in action. In the upcoming lessons, we shall build further on these ideas towards having a clear understanding of Bayesian Logic and its role in machine learning. 

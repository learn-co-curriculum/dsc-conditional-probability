
# Conditional Probability 

## Introduction


In the previous lessons and labs, you learned about some fundamentals of probability theory, along with basic combinatorics such as permutations and combitations. You'll now extend your knowledge on probability by learning about **Conditional Probability**. You'll see how Conditional Probability is extremely important in Statistics, and the foundation of many applications. Understanding conditional probability is essential when exloring fields in Machine Learning and Artificial Intelligence.

In this lesson, you'll learn about conditional probability, what it is, and how and when to use it. Later on, you'll see how this simple idea becomes a key component in most statistical machine learning algorithms. 

## Objectives 
You will be able to:

* Differentiate between independent and dependent random events 
* Understand and Explain the conditional probability: $P(A \cap B) = P(A\mid B)*P(B) $
* Use the multiplication rule to find the probability of the intersection of two events
* Understand and describe some important theorems based on conditional probabilities

## Events and Sample Space

Before introducing you to to specific event types, let's do a quick recap of the notion of event and sample space.

An **event** is the outcome of an experiment, for example, obtaining heads when tossing of a coin or getting 3 after a dice roll. Note: an event can also be a collection of different events grouped together (or a so-called **compound** event), eg. getting a 3 twice when rolling a dice twice.  

A **eample space** is a collection of every single possible outcome in a trial, generally represented by $\Omega$. 
The sample space for 1 random dice throw is  {1,2,3,4,5,6}. 


As you remember for the previous lessons, we can combine event and sample space to compute event probability.

You'll learn about 3 important event types: **independent**, **disjunct**, and **dependent** events.

### Independent Events

** Events $A$ and $B$ are independent when, the occurrence of $A$ has no effect on whether $B$ will occur (or not).**

Consider following independent events 

* Getting heads after flipping a coin **and** getting a 5 on throw of a fair dice
* Choosing a marble from a container **and** getting heads after flipping a coin

#### Two independent events

Formally, events A and B are independent if 
- $P(A \cap B) = P(A)P(B)$,  and
- $P (A \cup B) = P(A) + P(B) - P(A\cap B)$  

![](images/ind1.jpg)

#### Three independent events
Three events A, B and C if

- $P(A \cap B) = P(A)P(B)$ 
- $P(A \cap C) = P(A)P(C)$ 
- $P(B \cap C) = P(B)P(C)$
- $P(A \cap B \cap C) = P(A)P(B)P(C)$
 
So you need both *pairwise independence* and *three-way independence*

### Disjoint Events

**Events $A$ and $B$ are disjoint if $A$ occurring means that $B$ cannot occur.**

Disjoint events are **mutually exclusive**. $P (A \cap B)$ is **empty**.

![](images/disj.jpg)

### Dependent Events 

** Events $A$ and $B$ are dependent when, the occurrence of $A$ somehow has an effect on whether $B$ will occur (or not).**

Now things start getting a bit more interesting. 

Let's look at an example. Let's say event $A$ is taking a red or blue marble out of a jar. The jar contains 3 red and 2 blue marbles. 

<img src="images/marb.svg" width="300">

The probability of getting a blue marble is $\dfrac{2}{5}$ and getting a red marble is $\dfrac{3}{5}$.

<img src="images/cond3.gif" width="300">

At that point, one marble is taken out and we now take another marble from the jar (event $B$).

Here you can see that our second event is dependent on the outcome of first draw.

- If we drew a red marble first, the probability of getting a blue marble for event B is $\dfrac{2}{4}$. 
- If we saw a blue marble first, however, the probability of seeing a blue in second trial is $\dfrac{1}{4}$. 

In simple terms, the probability of seeing an event $B$ in the second trial depends on the outcome $A$ of the first trial. We say that $P(B)$ is **conditional** on $P(A)$.

A **tree diagram** can be used to explore all possible events.

<img src="images/tree.gif" width = 500>

## Conditional Probability 

> **Conditional Probability emerges in the examination of experiments where a result of a trial may influence the results of the upcoming trials.**

While calculating the probability of the second event (event B) given that the primary event (event A) has just happened, if there is a chance that A's outcome might have tempered with the sample space in some way, we can securely say that the probability of event B is reliant on the occurrence of event A.

Here are some more examples: 

* Drawing a 2nd Ace from a deck of cards given we got the initial Ace.
* Finding the probability of liking "Matrix" given the individual prefers science fiction.

If we consider event with P(A) as the probability of the event we are attempting to ascertain.
Event B is the condition that we know or the event that has happened.

We can compose the conditional probability (Probability of A **GIVEN** B) as :
$$ P (A \mid B) = \dfrac{P(A \cap B)}{P(B)}$$


> **P(A|B)**, the probability of the taking place of event A **given** that B has just happened. 

<img src="images/cond4.png" width=300>

Here’s how to derive the conditional probability equation shown above from the multiplication rule:

Step 1: Write out the multiplication rule:
* $P(A \cap B)= P(B)*P(A\mid B)$

Step 2: Divide both sides of the equation by P(B):
* $\dfrac{P(A \cap B)}{ P(B)} = \dfrac{P(B)*P(A\mid B)}{P(B)}$

Step 3: Cancel P(B) on the right side of the equation:
* $\dfrac{P(A \cap B)}{P(B)} = P(A \mid B)$

Step 4: This is of course equal to:
* $ P(A \mid B)=\dfrac{P(A \cap B)}{P(B)} $

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

>$P(A \cap B) = P(A|B) \ P(B)$

We can extend this for three variables:

>$P(A\cap B \cap C) = P(A| B \cap C) \ P(B \cap C) = P(A|B \cap C) \ P(B|C) \ P(C)$

and in general to n variables:

$$P(A1 \cap A2 \ \cap ... \cap \ An) = P(A1| A2 \cap ... \cap An) P(A2| \ A3\  \cap ... \cap \ An) P(An-1|An) P(An)$$

In general we refer to this as the chain rule.

If on the other hand, 

if $C_1, C_2,...,C_m$ are disjoint events such that $C_1\cup C_2\cup ··· \cup  C_m = \Omega$ the probability of an arbitrary event can be expressed as:

\begin{align}
P(A) = P(A | C_1)P(C_1) + P(A | C_2)P(C_2) + ··· + P(A | C_m)P(C_m)
\end{align}

## Theorem 3 - Bayes rule

The **Bayes theorem**, which is the outcome of this section. Below is the formula that we will dig deeper into , in upcoming lessons.

\begin{align}
    P(A|B) = \frac{P(B|A)P(A)}{P(B)} \text{-        this follows from Theorem 1}
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

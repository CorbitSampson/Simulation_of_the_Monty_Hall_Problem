# The Monty Hall Problem

---
---

## Introduction 

The famous "Monty Hall Problem" is a well-known example of the role of conditional problem that was made popular by the television game show *Let's Make a Deal*. In the problem, an individual is presented with a collection of three doors, behind one of which is a prize. The Individual is told to select one of these three doors, after which, the host opens one of the remaining unselected doors, showing that the prize is not behind said door. The individual is then asked if they would like to remain with their initial selection or switch to the remaining closed door that they did not originally select. The problem then is simply to determine if the individual should remain with their original door or swap to the remaining choice. 

While during the time of *Let's Make a Deal*, this problem resulted in a large amount of contention, particularly after the columnist Marilyn vos Savant wrote, in *Parade* magazine, that one should switch doors in the problem with her simple and very correct explanation. The magazine received approximately 10,000 letters, including a large portion of Ph.Ds., largely complaining that her explanation and solution were incorrect.

The solution proposed by Savant was a simple explanation that can be formally described using the condition problem, and is as follows:

1. The individual selects one of the three doors, let's call this door 1. The probability that door 1 has the prize behind it is $1/3$, meaning that the probability that the door does not have the prize is $1 - 1/3 = 2/3$.


2. Next, the host removes one of the remaining doors, say door 2. It is a rule of the game and an assumption of the problem that the host only removes a door that does not have the prize. Therefore, door 2 necessarily doesn't have the prize. Then the individual is prompted with the choice to change doors.


3. There are now two doors remaining. Door 1, selected by the individual, which has a probability of $1/3$ to contain the prize and $2/3$ that it does not, and Door 3, which has a probability of will have probabilities $1-1/3=2/3$ of containing the prize and $1-2/3=1/3$ of not containing the prize. Note that these are the conditional probabilities given that the initial choice was made.  

Therefore, we are left that switching doors leads to a higher probability of a favorable outcome for exactly the reason that you were less likely to guess the correct door initially.


References statement:

While the following code was written and prepared by me, the above historical details were collected from Wikipedia and can be found, along with many others, here: [Wiki: Monty Hall Problem](https://en.wikipedia.org/wiki/Monty_Hall_problem#Solutions_using_conditional_probability_and_other_solutions)

--- 

## The purpose of this notebook

If anyone is to stumble upon this notebook on my GitHub account, they may ask, "Why did you write this if this is already well understood?". Well, as mentioned in the introduction, this solution caused considerable confusion and contention from readers of Savant's column, even from many mathematicians. This includes the famous example of Paul Erdos, who only believed the result after seeing the results of numerical simulation. One would think that this matter had long been brought to rest; however, several months back, I was at a party. Among others, the guest list of this party included, including myself, 3 Ph.D. mathematicians, at least 2 holders of M.S. in applied mathematics, and several other highly educated individuals. A friend of one of these guests was very insistent that the well-accepted solution to the Monty Hall Problem was incorrect, despite receiving an explanation from just about every one of us. He was also very against creating a simulation of the result to see for himself that he was wrong. So here I am, about 7:00 pm on a holiday, putting the finishing touches on this notebook that contains a simulation of the Monty Hall problem compared with the theoretical result and a small mound of evidence that Savant's solution is correct. Hopefully, if you are ever so unfortunate as to run into an individual who refuses to believe Savant's solution, then you might find this notebook and be able to show them otherwise. Not that they are likely to believe me either. So good luck.

Dr. Corbit R. Sampson

--- 

## The content of this notebook

The following code block contains the necessary code to run a simulation of the Monty Hall problem for a user-selected sample size and number of samples. There is minor functionality to include more than 3 total doors. 

The primary run function is titled `main`. Note the code block below, as limited additional comments to explain details. Running the main function with `NumTrails = 1000` and `NumSamples = 1000` will cause 2000 simulations (1000 with door swaps 1000 without), each containing 1000 trails of the random process, plot the success and failure rates with and without door swaps and show the predicted values from the theory as dashed black lines. Additionally, the bar graph includes the $5\%$ confidence interval, assuming that the distribution of the samples is normal about the mean. Note that while `main` works from an arbitrary number of doors, the theory that was included in this function assumes only a SINGLE prize and will not produce the correct result.

In case anyone that you might be showing these simulations to doubts that the samples are normally distributed about the mean, and thus the selected method of creating the $5/%$ confidence interval would be a poor choice, the function `show_stat_fit` produces histograms of the outcome, with and without door swaps, and a normal distribution with the mean and standard deviation equal to the sample mean and sample standard deviation to see that this is an adequate distribution.

Lastly, the function `show_stat_fit` includes a brief analysis of what happens for a single prize behind an arbitrary number of doors, with and without door swaps. Particularly, showing that as the number of doors increases, the decision to swap doors begins to become moot, provided only a single door is taken away.

---

## uses

The intended uses for this notebook are exactly what I described above, to provide just a little more evidence to those who refuse to accept the long, long accepted solution to the Monty Hall Problem. In addition to this, please use the code to learn whatever you can from it, while that may be quite minor.

---


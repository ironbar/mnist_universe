# Causality

## [The Book of Why](https://www.amazon.com/Book-Why-Science-Cause-Effect/dp/046509760X)

The goal is to relate that to current NN models that do not interact with the world.

### 1. The Ladder of causation

#### Ladder of causation

>First, very early in our evolution, we humans realized that the world is not made up only of dry facts(what we might call data today); rather these facts are glue together by an intrincate web of cause-effect relationships. 
>Second, causal explanations, not dry facts, make up the bulk of our knowledge, and should be the cornerstone of machine intelligence.

![ladder_causation](https://hpccsystems.com/wp-content/uploads/2022/09/Ladder-1.png)

> The goal of strong AI is to produce machines with humanlike intelligence, able to converse with and guide humans. Deep Learning has instead given us machines with truly impressive abilities but no intelligence. The difference is profound and lies in the absence of a model of reality.

> The lack of flexibility and adaptability is inevitable in any system that works at the first level of the ladder of causation

> A sufficiently strong and accurate causal model can allow us to use rung-one (observational) data to answer rung-two (interventional) queries

#### Cognitive revolution

> The Lion Man is a 40k year old sculpture. Is different from previous art because is a creature of previous imagination. Within 10k years after the Lion Man's creation all other hominids had become extinct.

> Humans evolved from apelike ancestors over a period of 6 million years. But in roughly the last 50k years something unique happened, which some call the Cognitive Revolution. Humans acquired the ability to modify their environment and their own abilities at a dramatically faster rate.

> Their newly acquired causal imagination enabled them to do many things more efficiently through a tricky process called "planning".

#### Probability

> Decades' worth of experience with these kinds of questions has convinced me that, in both a cognitive and a philosophical sense, the idea of causes and effects is much more fundamental than the idea of probability. We begin learning causes and effects before we understand language and before we know any mathematics.

> Probabilities, as given by expressions like `P(Y|X)', lie on the first rung of the Ladder of Causation and cannot ever (by themselves) answer queries on the second or third rung. 

> While probabilities encode our beliefs about a static world, causality tells us whether and how probabilities change when the world changes, be it by intervention or by act of imagination.


### 2. From Buccaneers to Guine Pigs

This chapter tells the history of how the dominant school of thought in statistics banned causality from science and instead advocated for correlation. It's interesting to see the influence of eminent statiticians. It also tells how Wright battled with them with his path analysis technique.

#### Regression to the mean

#### History of Pearson and his preference for correlation over causation

#### Guinea pigs

![guinea-pig-path-analysis](http://jacheung.com/images/latest/path-analysis/guinea-pig-path-analysis.png)

> You cannot draw causal conclusions without some causal hypotheses.This echoes what we concluded in Chapter 1: you cannot answer a question on rung two of the ladder of causation using only data collected from rung one.

### 3. From Evidence to Causes: Reverend Bayes meets Mr Holmes

#### Bayes theorem

> Bayer theorem shows that you can deduce the probability of a cause from an effect. If we know the cause it is easy to estimate the probability of the effect, which is a forward probability. Going the other direction is harder.

For example if we have covid then we know the probability of having a positive result in a covid test (simply look at the FNR of the test). However computing the probability of having covid given that we know that the result of the test is positive is not straitghtforward.

> We can estimate the conditional probability directly in one direction, for which our judgment is more reliable, and use mathematics to derive the conditional probability in the other direction, for which our judgment is rather hazy.

$$ P(C|T) P(T) = P(T|C) P(C) $$

$$ P(C|T) = \frac{P(T|C) P(C)}{P(T)} = \frac{P(T|C)}{P(T)} P(C) $$

$$ P(C|T) = \frac{(1-FNR) P(C)}{(1-FNR) P(C) + FPR P(\neg C)} $$

With that equation we can compute the probability of having covid given that the result of the test was positive.

There is an interesting example of mammogram test to check for breast cancer.

Bayes theorem allows to update our prior belief about something using new information. The likelihood ratio modifies the initial belief.

$$ P(C|T) = \frac{P(T|C)}{P(T)} P(C) $$

$$ likelihood ratio = \frac{P(T|C)}{P(T)} $$

Then there is a tiny glimpse at bayesian networks

> I felt convinced that any artificial intelligence would have to model itself on what we know about human neural information processing and that machine reasoning under uncertainty would have to be constructed with a similar message passing architecture. But what are the messages? This took me quite a few months to figure out. I finally realize that the messages were conditional probabilities in one direction and likelihood ratios in the other.

#### Bayesian networks

> A bayesian network carries no assumption that the arrow has a causal meaning. The arrow merely signifies that we know the "forward" probability. Baye's rule tells us how to reverse the procedure, specifically by multiplying the prior probability by a likelihood ratio.

[Bayesian network on wikipedia](https://en.wikipedia.org/wiki/Bayesian_network)

| Pattern  | Model                         |
|----------|-------------------------------|
| Chain    | $A\rightarrow B\rightarrow C$ |
| Fork     | $A\leftarrow B\rightarrow C$  |
| Collider | $A\rightarrow B\leftarrow C$  |

> Chain junction. In science one often thinks of B as the mechanism, or mediator that transmits the effect of A to C. A familiar example is Fire $\rightarrow$ Smoke $\rightarrow$ Alarm

> Fork junction. B is often called a confounder of A and C. The confounder will make A and C statistically correlated even thought there is no direct causal link between them. A good example is Shoe Size $\leftarrow$ Age of child $\rightarrow$ Reading ability

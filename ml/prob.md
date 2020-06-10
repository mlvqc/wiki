# Probabilistic Programming and Bayesian Methods for Hackers 

-- Recommended on tensorflow_probability home page.

## The Bayesian state of mind

Suppose you write some code and you believe it works but you are not completely sure. So you write so tests and the code passes. Based on this your confidence in your code improves. However, give that your tests are finite you still are not 100% confident in your code. 

This is your mind performing Bayesian inference. Mathematically your mind has so prior assumption that your code has bugs $$P(\text{bug})$$. You also assign a confidence in your tests, so that the probability a bug slipped through your tests while they still all passed is $$P(\text{passed}|\text{bug})$$. Therefore, the confidence, or posterior, that there is a bug given that all the tests are passed is
$$
P(\text{bug}|\text{passed}) = \frac{P(\text{passed}|\text{bug}) P(\text{bug})}{P(\text{passed})}
$$
The probability that the code passes the test is given by
$$
P(\text{passed}) = P(\text{passed}|\text{bug}) P(\text{bug}) +  P(\text{passed}|\text{ no bug}) P(\text{no bug})
$$

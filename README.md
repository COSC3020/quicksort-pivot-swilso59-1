[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Answer
For the leftmost we can see that there is a 1/2 chance of picking a good pivot or bad pivot. The bad pivot can be either to high or to low which leaves us with a 1/4 chance being high or low. 

In the median-of-three method there is a 1/2 chance of picking a bad pivot that is lower or higher then this leaves us with a 1/2 chance of picking a good pivot. This makes it equal chances of picking a good or bad pivot on our first choice. If we are using the median of three method we do not know exactly what the three choices would be so we have to look at all the different possible combinations. Here L will represent a pivot that is too low, G will represent a pivot that is good, and H will represent a pivot that is high. We know the chance of picking a pivot that is low is 1/4, a pivot that is high is 1/4, and a pviot that is good is 1/2. 
we want to find all the ways we can pick 3 pivots and there probabilities:
- $GGG = (\frac{1}{2})^{3} = \frac{1}{8}$
- $GGH = (\frac{1}{2})^{2}\times(\frac{1}{4}) = \frac{1}{16}$
- $LGG = (\frac{1}{4})\times(\frac{1}{2})^{2} = \frac{1}{16}$
- $LGH = (\frac{1}{4})\times(\frac{1}{2})\times(\frac{1}{4}) = \frac{1}{32}$
- $GHH = (\frac{1}{2})\times(\frac{1}{4})^{2} = \frac{1}{32}$ 
- $LLG = (\frac{1}{4})^{2}\times(\frac{1}{2}) = \frac{1}{32}$
- $HHH = (\frac{1}{4})^{3} = \frac{1}{64}$
- $LHH = (\frac{1}{4})^{3} = \frac{1}{64}$
- $LLH = (\frac{1}{4})^{3} = \frac{1}{64}$
- $LLL = (\frac{1}{4})^{3} = \frac{1}{64}$

Now for each combination find the common denomenator and multiply by the number of permutations. 

- $GGG = \frac{8}{64}$ only one permutation
- $GGH = \frac{12}{64}$ since there are 3 permutations
- $LGG = \frac{12}{64}$ since there are 3 permutations
- $LGH = \frac{12}{64}$ since there are 6 permutations
- $GHH = \frac{6}{64}$ since there are 3 permutations
- $LLG = \frac{6}{64}$ since there are 3 permutations 
- $HHH = \frac{1}{64}$ only one permutation
- $LHH = \frac{3}{64}$ 3 permutations
- $LLH = \frac{3}{64}$ 3 permutations
- $LLL = \frac{1}{64}$ only 1 permutation

Now we can add up the combinations that would be considered a good pivot to get the chance of picking a good pivot using the median-of-three method. This gives us a 68.75% chance of picking a good pivot. Which means it is a higher chance of picking a good pivot using this method then the left most pivot which is a 50% chance. 


- quicksort-pivot-ZachRenz
- quicksort-pivot-IshitaPatel18

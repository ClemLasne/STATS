# AIC model selection and multimodel inference in behavioral ecology: some background, observations, and comparisons.
### Behav.Ecol.Sociobiol 65:23-35
### DOI: 10.1007/s00265-010-1029-6

*Super interesting paper about the advantages of the **information theory** approach over the tradition statistical tests such as anova and the p-value approach.*

Some key points:

## Introduction
> The standard practice so far has been to define a single alternative hypothesis and to test it against a null hypothesis. An alternative is think of several plausible alternative hypotheses (models) and to evaluate the relative **strenght of evidence** for each hypothesised model.

**TRADITIONAL METHODS**
> Traditional methods have focused on *testing* null hypotheses based on test statistics and their associated *P* values. From *P* values comes an arbitrary judgment concerning "statistical significance" and dichotomous ruling about the **rejection of, or failure to reject, the null hypothesis**. Fore several reasons, *P* values do not consistute a basis for formal evidence. (see Royall 1997)

**INFORMATION THEORY (I-T)**
> The I-T methods provide a formal fundamentally sound appraoch of developping an *a priori* set of hypotheses and then a quantification of the data-based evidence for, and ranking of each hypothesis. This is followed by **interpretation** of the result in the face of model selection uncertainty, one aspect of **multimodel inference**. 

## Fundamentals
> What we want is a model from within a model set that loses the least information about full reality, hence, the model hat is the closest to full reality in the current set. The **best model** is *NOT* the model that "best fits the data" but rather the model that **"minimizes the loss of information"** about the dataset. This model has the smallest AIC score.

**AIC**

*find another ref for that* but it uses log-likelyhood (LL) .

**Delta AIC**

Δ<sub>i</sub> = AICc<sub>*i*</sub> - AICc<sub>*min*</sub>, for *i* = 1, 2, 3, ... *R* models

* AICc = AIC corrected for small sample size

* AICc<sub>*min*</sub> = the minimum AICc value of all of the R models. The model is the model of the model set that loses the least information about the data, or the model that has the smallest distance to "full reality". 

* AICc<sub>*i*</sub> = the AICc value of the model looked at

Δ<sub>i</sub> > 7 --> model i has very little empirical support

Δ<sub>i</sub> > 20 --> model i has no empirical support

**Relative Likelihood of a model**

AI Overview: 
> The relative likelihood compares the plausibility of different models or parameter values given a set of data, aiding in model selection and hypothesis testing by quantifying the strength of evidence for one model over another. The relative likelihood based on AIC is not a true likelihood, but rather a measure of relative model fit

RL = `exp(-(AIC_i - AIC_min)/2)`

* RL close to 0 --> model i is bad relative to model with min AIC
* RL close to 1 --> model i and model with min AIC are not that different *find better way of phrasing it*

From the paper: 
> The quantities allow evidentiary statements such as "model/ hypothesis H3 is x times more likely than H7" for example.

From https://stats.stackexchange.com/questions/383567/calculating-the-relative-likelihood-with-aic-values:
> AIC weights can also be useful as they serve to normalize the relative likelihoods from a set of candidate models. Also, AIC weights allow quantification of the relative probability that a model is correct (relative to the other models considered) for the given data.



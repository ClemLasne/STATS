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

**1. Delta AIC**

Δ<sub>i</sub> = AICc<sub>*i*</sub> - AICc<sub>*min*</sub>, for *i* = 1, 2, 3, ... *R* models

* AICc = AIC corrected for small sample size

* AICc<sub>*min*</sub> = the minimum AICc value of all of the R models. The model is the model of the model set that loses the least information about the data, or the model that has the smallest distance to "full reality". 

* AICc<sub>*i*</sub> = the AICc value of the model looked at

Δ<sub>i</sub> > 7 --> model i has very little empirical support

Δ<sub>i</sub> > 20 --> model i has no empirical support

**2. Relative Likelihood of a model**

AI Overview (based on Burnham and Anderson): 
> The relative likelihood **compares the relative plausibility of different candidate models or parameter values given a set of data, based on AIC values** aiding in model selection and hypothesis testing by quantifying the strength of evidence for one model over another. The relative likelihood based on AIC is not a true likelihood, but rather a measure of relative model fit.

RL = `exp((AIC_min - AIC_i)/2)`

* RL close to 0 --> model i is bad relative to model with min AIC
* RL close to 1 --> model i and model with min AIC are similar in terms of fit

From the paper: 
> The quantities allow evidentiary statements such as "model/ hypothesis H3 is x times more likely than H7" for example.

**3. AIC (Akaike) weights**

> Akaike weights provide a measure of model selection uncertainty, representing the probability that a specific model is the "best" model in the set. From the Burnham, Anderson and Huyvaert paper, it is also called the "model probability" - which is a poor choice of words - as they mean *"the probability of each model of being the best model GIVEN the set of models"*  

From https://stats.stackexchange.com/questions/383567/calculating-the-relative-likelihood-with-aic-values:
> AIC weights can also be useful as they serve to normalize the **relative likelihoods from a set of candidate models**. Also, AIC weights allow quantification of the relative probability that a model is correct (relative to the other models considered) for the given data.

Akaike weight = Relative Likelihood / Sum of all Relative Likelihoods. 

Example from the paper: if *w<sub>i</sub>* = 0.99, we can be sure that this really is the best model in the set of models tested. But if *w<sub>i</sub>* = 0.43, there is considerable uncertainty in the data-based selection of the best model.

**4. Evidence ratio**

Looking at the ratio of model weights between 2 models *i* and *j* can help determining how strong the empirical evidence is for one model relative to another. 

From R documentation website on the `aictab` R function we use: 
https://www.rdocumentation.org/packages/AICcmodavg/versions/2.3-3/topics/aictab
> the Akaike weights, also termed "model probabilities" sensu Burnham and Anderson (2002) and Anderson (2008). These measures indicate the level of support (i.e., weight of evidence) in favor of any given model being the most parsimonious among the candidate model set.

Example from the paper
> If *w<sub>3</sub>* = 0.78 and *w<sub>1</sub>*= 0.015, 0.78/0.015 = 52, "the empirical support for model 3 is 52 times that of model 1" or "The evidence is 52 times stronger for model 3 than it is for model 1" or "the evidence ration for model 3 over model 1 is 52 to 1". 


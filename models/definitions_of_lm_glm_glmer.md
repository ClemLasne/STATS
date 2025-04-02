What is the difference between linear models (lm), generalised linear models (glm) and generalized mixed effect models (glmer) ?

## AIs Overviews reponse:

lm models linear relationships with normally distributed errors, glm extends this to non-normal errors and non-linear relationships through link functions, and glmer adds random effects to glm models, suitable for hierarchical or clustered data. 
Here's a more detailed breakdown:

### 1. Linear Models (lm):
Purpose: Models the relationship between a dependent variable and one or more independent variables, assuming a linear relationship and normally distributed errors.

Assumptions:
* Linearity: The relationship between the predictor and response variables is linear.
* Independence: Observations are independent of each other.
* Homoscedasticity: The variance of the errors is constant across all levels of the predictor variables.
* Normality: The errors are normally distributed.

*Example: Predicting house prices based on size and location.*

### 2. Generalized Linear Models (glm):
Purpose: Extends linear models to handle non-normal error distributions and non-linear relationships.

Key Features:
* Link Function: Allows for non-linear relationships between the predictor variables and the mean of the response variable.
* Error Distributions: Can handle various error distributions beyond the normal distribution, such as binomial (for binary outcomes), Poisson (for count data), etc.

*Example:
Logistic Regression: Predicting the probability of a binary outcome (e.g., success/failure).
Poisson Regression: Modeling the count of events over a period.*

R Package: `stats` package. 

### 3. Generalized Linear Mixed Models (glmer):
Purpose:Combines the flexibility of GLMs with the ability to model random effects, useful for hierarchical or clustered data.

Key Features:
* Random Effects: Allows for random intercepts and/or slopes, accounting for variability between groups or individuals.
* Fixed Effects: Includes fixed effects, which are the same for all groups or individuals.

R Package: `lme4` package.

*Example: Modeling student performance, where students are nested within classrooms (random effect) and schools (random effect), while also including predictors such as test difficulty (fixed effect).*

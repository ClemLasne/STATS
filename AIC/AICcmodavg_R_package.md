There is an R package that compares the AICs of all of the possible models created by a user to explain the variance observed in a dataset. 

In R: 

```ruby
install.packages("AICcmodavg")
library(AICcmodavg)
```
R documentation page about this package: https://www.rdocumentation.org/packages/AICcmodavg/versions/2.3-3/topics/aictab

# how it works

Make a list of all of the possible models explaining the variance in your dataset, from the simplest to the most complex. Make a list object contact these models, and then run this list through the package.

Example:

```ruby
age.mod <- lm(bmi ~ age, data = bmi.data)
sex.mod <- lm(bmi ~ sex, data = bmi.data)
consumption.mod <- lm(bmi ~ consumption, data = bmi.data)
age.sex.mod <- lm(bmi ~ age + sex, data = bmi.data)
combination.mod <- lm(bmi ~ age + sex + consumption, data = bmi.data)
interaction.mod <- lm(bmi ~ age*sex*consumption, data = bmi.data)

# make the list of models
models <- list(age.mod, sex.mod, consumption.mod, age.sex.mod, combination.mod, interaction.mod)

# give them names that will facilitate your understanding of the resulting table
model.names <- c('age.mod', 'sex.mod', 'consumption.mod', 'age.sex.mod', 'combination.mod', 'interaction.mod')

# run the list of models in the package
aictab(cand.set = models, modnames = model.names)
```

You obtain a table like this: 

![Screenshot 2025-04-02 at 12 00 44](https://github.com/user-attachments/assets/46d976e0-a61e-474e-8c96-f22a55f3525a)

Source of information for this package : https://www.scribbr.com/statistics/akaike-information-criterion/


# Burnham, Anderson and Huyvaert 2011. 
## AIC model selection and multimodel inference in behavioral ecology: some background, observations, and comparisons

Super interesting paper about the advantages of the **information theory** approach over the tradition statistical tests such as anova and the p-value approach.

Some key points:
> The standard practice so far has been to define a single alternative hypothesis and to test it against a null hypothesis. An alternative is think of several plausible alternative hypotheses (models) and to evaluate the relative **strenght of evidence** for each hypothesised model.


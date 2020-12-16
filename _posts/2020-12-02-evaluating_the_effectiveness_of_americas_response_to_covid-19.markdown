---
layout: post
title:      "Evaluating the Effectiveness of America's Response to COVID-19"
date:       2020-12-02 14:08:01 -0500
permalink:  evaluating_the_effectiveness_of_americas_response_to_covid-19
---


Machine learning is being used to understand coronavirus, accelerate public policy solutions and minimize its impact on human health. Of the ample research studies on COVID-19, I was specifically interested in whether the United States’ policy response to COVID-19 was adequate in weathering the rapidly exacerbating pandemic storm. Malik Magdon-Ismail’s research was especially interesting because of its use of a simple but robust regression model to generate tested predictions on the pandemic trend from early U.S. data. In this blog, I will explain some of the key elements and findings from his research. 

**Background:** 
At the time of publishing his paper on 04/10, aggressive policies were in effect (social distancing on 03/13 and lockdowns around 03/21). This means the effectiveness of those policies could be measured starting 03/23 and 03/31 respectively (t+10). Malik’s results show that these measures were indeed effective in ‘flattening the curve’; actual data observed on COVID-19 cases after t+10 social distancing policies were statistically significantly lower than the predicted spread from early data numbers. Starting on about March 25, the observed infections start falling off and we observe a flattening by March 28.

**Experiment:**
To arrive at his results, Malik uses machine learning to model the early dynamics of COVID-19 on the first 54 days of CDC confirmed infection reports, extrapolates predictions using that early training data, and then compares those predictions to actual numbers post social distancing. The usage of early (pre-policy) COVID-19 data is key; it allows us to avoid the statistical correlations that can result from human intervention and invalidate regression results (i.e. public health protocols such as randomized testing). 

The model takes into account 4 variables, defined as the following:
- β (asymptomatic force) - portion of people who are sick, but do not show symptoms, thusly dreading the disease exponentially
- V (virulence) - proportion of mild cases that become serious
- K (incubation time) - the lag time for virulence to take effect 
- Mo (unconfirmed asymptomatic infections) - the number of unknown infections at the Time = 0 

It’s worth noting that the use of U.S. training data would not be applicable in generating predictions for another nation. Genetic and demographic factors, as well as thresholds on what “serious” means for another culture, can require re-calibration.

**Machine Learning:**
In order to arrive at the optimal parameters which are most likely to generate probable predictions, Malik uses gradient descent and perturbation analysis. Gradient descent iteratively starts with a random set of values and improves them slowly by minimizing the cost function. It does this by calculating the gradient (or derivative) of the cost, and then moves in the opposite direction of that gradient to reduce the cost until it arrives at the optimal point past which the cost can no longer be reduced. He also uses perturbation analysis to understand how a small change in any one parameter affects how well the model is trained.

The primary application of these methods is in guesstimatating the asymptomatic force, β. Malik has to deduce this variable using math. Otherwise, how else would we estimate what the true number of asymptomatic cases really is, if we never really know or see all of the people who are not showing any symptoms? Mathematically, he uses the given k and M0 to get an approximate fit to the data (using a perturbation analysis), and from there, solves for the γ & β that fit two points on the time frame S(τ) and S(T). He then optimizes γ, β using gradient descent. In a nutshell, he reverse engineers the data he has, to deduce β, the data he does not have. Ultimately, this produces a large margin of error; the model generates 5.3m of asymptomatic cases on 3/14 - but the true number could really be anywhere from [1.3, 26] million.


In order to measure the predictability of his model, Malik uses root-mean-squared-error (RMSE), taken between the observed early dynamics and model predictions. RMSE is the standard deviation of the difference between the real and predicted data, or the residuals. Hence, it tells you how different the real and predicted value are, or how close your model is to the truth. Ultimately, he also uses R^2, to measure how close the data is to his fitted regression line. Malik arrives at an R^2 is 0.57, indicating his cross-validation-based linear model captures 57% of the residual variance. A simpler way to interpret this R^2 would be that his model accurately predicts a future case of COVID-19 57% of the time. 




**Results**
Malik’s model resulted in the following parameter figures for the U.S: 

*β = 1.30 *

- The asymptomatic infectious force, β, is very high; the number of COVID-19 cases double every 2.6 days (people are still contagious without exhibiting symptoms, allowing the infection to spread if left unchecked)
- 30% of cases are asymptomatic, converting to serious 1.2% of the time 

*γ = 0.0014 
*
- A virulence of 0.14% is comparable to the standard flu, albeit not as critical for specific age groups 
- 1-2 out of 100 people’s conditions will convert to very serious

*k = 10 days *

- The incubation period of 10 days is in line with physician observations (it takes 10 days on average for one’s symptoms to surface)
-	However, there is also significant uncertainty in the lag, from 1 up to 13 days

*M0 = 4 *

- The data analysis predicts an intercept of 4 at T = 0 (when the first confirmed case appeared, there were 4 other unknown infections in the U.S.)

Malik also finds that severity of COVID-19 can vary tremendously by nation, due to factors idiosyncratic to the data in a said location:
-	Spread is much faster in poorer countries (fewer resources to inhibit spread)
-	Spread is faster in younger countries (younger people are more mobile, more likely to spread)
-	Population density at the initial infection site have strong positive weights (if people are closer, its more likely to spread)
-	Age has a strong negative weight (more likely to get COVID-19 if older, assuming immunity is weaker)
-	Wealth and income have weak negative effects (greater resources, space, access to care etc.)

**Current State:**
I was curious whether the trends Malik observed have persisted since this paper was published. To find out, I looked at one (of many) COVID-19 dashboards listing the latest numbers. As of 04/14, there are 607, 000 confirmed cases in the United States. Malik supplies predictions as late as 04/14, at 2,180,000 cases. That is, 28% of the predicted cases have manifested. This makes the key assumption that everyone who has COVID-19 has been tested. Seeing this drastic difference between predictions and actuals, we could stretch to say social-distancing policies have effectively avoided the other 72% of potential cases we would otherwise have without those measures. While these policies are working, they are not working as effectively as they should; 607,000 is still too many. The U.S. needs to more rigorously incentivize social distancing, testing and contact tracing to suppress the asymptomatic force β, until a secondary outbreak is no longer likely. 



This blog was originally published on 04/14/20



**Sources:**

Research paper: [Machine Learning the Phenomenology of COVID-19 From Early Infection Dynamics](http://www.medrxiv.org/content/10.1101/2020.03.17.20037309v3)

COVID-19 Dashboard: [{Coronavirus} Package](https://ramikrispin.github.io/coronavirus_dashboard/)



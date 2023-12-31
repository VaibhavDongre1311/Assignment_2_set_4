# Topics: Sampling Distributions and Central Limit Theorem


## 1) Examine the following normal Quantile plots carefully. Which of these plots indicates that the data …
	
  ![image](https://user-images.githubusercontent.com/99672298/158005525-53b401f9-b024-413a-84ef-6b80761c8cce.png) \

Are nearly normal?\
Ans => C\
	Have a bimodal distribution? (One way to recognize a bimodal shape is a “gap” in the spacing of adjacent data values.) => B and D\
	Are skewed (i.e. not symmetric)? =>A,B and D\
	Have outliers on both sides of the center? => A and B

 


## 2) For each of the following statements, indicate whether it is True/False. If false, explain why.

The manager of a warehouse monitors the volume of shipments made by the delivery team. The automated tracking system tracks every package as it moves through the facility. A sample of 25 packages are selected and weighed every day. Based on current contracts with customers, the weights should have μ = 22 lbs. and σ = 5 lbs.

### i) Before using a normal model for the sampling distribution of the average package weights, the manager must confirm that weights of individual packages are normally distributed.
Ans: False 
: it is invalid to take a weight of individual packages and confirm that it follows normal distribution before using a normal model for the sampling distribution. The Sample Central Limit Theorem states that the sampling distribution of the samples mean approaches normal distribution as the sample size is large enough.

### ii) The standard error of the daily average SE(x ̅) = 1.
Ans: True :
 As SE(Standard Error)  =  sample standard deviation / Square root of (number of sample)
Standard error is sample standard deviation / Square root of (number of sample) So SE=1

### iii) Auditors at a small community bank randomly sample 100 withdrawal transactions made during the week at an ATM machine located near the bank’s main branch. Over the past 2 years, the average withdrawal amount has been $50 with a standard deviation of $40. Since audit investigations are typically expensive, the auditors decide to not initiate further investigations if the mean transaction amount of the sample is between $45 and $55. What is the probability that in any given week, there will be an investigation?

	1.25%
	2.5%
	10.55%
	21.1%
	50%

Ans: D

import scipy.stats as stats

import numpy as np

mean = 50

std = 40

n = 100

the population standard deviation 

p_std=40/np.sqrt(100) 

lower = 45

upper = 55

z_lower = (lower - mean) / p_std

z_upper = (upper - mean) / p_std

Compute the probability of the sample mean being between the lower and upper limits

prob = stats.norm.cdf(z_upper) - stats.norm.cdf(z_lower)

probailty that in any given week, there will be an investigation

proba=1-prob

precentage=proba*100

print(proba)

probailty that in any given week, there will be an investigation is 21.1%

## 4 ) The auditors from the above example would like to maintain the probability of investigation to 5%. Which of the following represents the minimum number transactions that they should sample if they do not want to change the thresholds of 45 and 55? Assume that the sample statistics remain unchanged.

	144
	150
	196
	250
	Not enough information
 
Ans:  D
t_value=stats.t.ppf((1-0.05/2),99)

t_value

n=(40*1.96)**2/25

print(n)  

n=248 

## 5) An educational startup that helps MBA aspirants write their essays is targeting individuals who have taken GMAT in 2012 and have expressed interest in applying to FT top 20 b-schools. There are 40000 such individuals with an average GMAT score of 720 and a standard deviation of 120. The scores are distributed between 650 and 790 with a very long and thin tail towards the higher end resulting in substantial skewness. Which of the following is likely to be true for randomly chosen samples of aspirants?

+ The standard deviation of the scores within any sample will be 120.
+	The standard deviation of the mean of across several samples will be 120.
+	The mean score in any sample will be 720.
+	The average of the mean across several samples will be 720.
+	The standard deviation of the mean across several samples will be 0.60
  
Ans: E 
Standard error = sigma / (n)^0.5
                            = standard deviation / (sample size)^0.5
                            = 120 / (40000)^0.5
                            = 0.6

# Learn_hypothesis_testing_for_Data_science

## Understanding Confidence Intervals

When you make an estimate in statistics, whether it is a summary statistic or a test statistic, there is always uncertainty around that estimate because the number is based on a sample of the population you are studying.

The confidence interval is the range of values that you expect your estimate to fall between a certain percentage of the time if you run your experiment again or re-sample the population in the same way.

The confidence level is the percentage of times you expect to reproduce an estimate between the upper and lower bounds of the confidence interval, and is set by the alpha value.

The alpha value, or the threshold for statistical significance, is arbitrary – which value you use depends on your field of study.

In most cases, researchers use an alpha of 0.05, which means that there is a less than 5% chance that the data being tested could have occurred under the null hypothesis.

### What exactly is a confidence interval?
A confidence interval is the mean of your estimate plus and minus the variation in that estimate. This is the range of values you expect your estimate to fall between if you redo your test, within a certain level of confidence.

Confidence, in statistics, is another way to describe probability. For example, if you construct a confidence interval with a 95% confidence level, you are confident that 95 out of 100 times the estimate will fall between the upper and lower values specified by the confidence interval.

Your desired confidence level is usually one minus the alpha ( $\alpha$ ) value you used in your statistical test:

Confidence level = 1 − $\alpha$

So if you use an alpha value of p < 0.05 for statistical significance, then your confidence level would be 1 − 0.05 = 0.95, or 95%.

When do you use confidence intervals?
You can calculate confidence intervals for many kinds of statistical estimates, including:

+ Proportions
+ Population means
+ Differences between population means or proportions
+ Estimates of variation among groups

These are all point estimates, and don’t give any information about the variation around the number. Confidence intervals are useful for communicating the variation around a point estimate.

![image](https://user-images.githubusercontent.com/99672298/192198361-447bf8b8-07f3-4ba9-a61a-c9994c2177e6.png)

### Calculating a confidence interval: what you need to know
Most statistical programs will include the confidence interval of the estimate when you run a statistical test.

If you want to calculate a confidence interval on your own, you need to know:

A.) The point estimate you are constructing the confidence interval for
B.) The critical values for the test statistic
C.) The standard deviation of the sample
D.) The sample size

Once you know each of these components, you can calculate the confidence interval for your estimate by plugging them into the confidence interval formula that corresponds to your data.

Point estimate
The point estimate of your confidence interval will be whatever statistical estimate you are making (e.g. population mean, the difference between population means, proportions, variation among groups).

![image](https://user-images.githubusercontent.com/99672298/192200318-49be0d79-9b64-434f-947c-5b3e9044cd54.png)

Finding the critical value
Critical values tell you how many standard deviations away from the mean you need to go in order to reach the desired confidence level for your confidence interval.

There are three steps to find the critical value.

Choose your alpha ( $\alpha$ ) value.
The alpha value is the probability threshold for statistical significance. The most common alpha value is p = 0.05, but 0.1, 0.01, and even 0.001 are sometimes used. It’s best to look at the papers published in your field to decide which alpha value to use.

Decide if you need a one-tailed interval or a two-tailed interval.
You will most likely use a two-tailed interval unless you are doing a one-tailed t-test.

For a two-tailed interval, divide your $\alpha$ alpha by two to get the alpha value for the upper and lower tails.

Look up the critical value that corresponds with the alpha value.
If your data follows a normal distribution, or if you have a large sample size (n > 30) that is approximately normally distributed, you can use the z-distribution to find your critical values.

For a z-statistic, some of the most common values are shown in this table:

![image](https://user-images.githubusercontent.com/99672298/192200443-926b81c9-11b1-42f8-b8d6-cedb03af839c.png)

If you are using a small dataset (n ≤ 30) that is approximately normally distributed, use the t-distribution instead.

The t-distribution follows the same shape as the z-distribution, but corrects for small sample sizes. For the t-distribution, you need to know your degrees of freedom (sample size minus 1).

For normal distributions, like the t-distribution and z-distribution, the critical value is the same on either side of the mean.

![image](https://user-images.githubusercontent.com/99672298/192200704-a60b50f3-a6cd-4973-bdcd-bd2cd1bc09c0.png)
![image](https://user-images.githubusercontent.com/99672298/192200740-38b7f481-355d-42bd-bd11-867d56a0c3de.png)
![image](https://user-images.githubusercontent.com/99672298/192200863-4b61dbb3-5d84-4d44-bee0-b3933179a765.png)
![image](https://user-images.githubusercontent.com/99672298/192200964-1d2644f6-835f-4a98-a6b0-112a1b6e9995.png)

### Caution when using confidence intervals
Confidence intervals are sometimes interpreted as saying that the ‘true value’ of your estimate lies within the bounds of the confidence interval.

This is not the case. The confidence interval cannot tell you how likely it is that you found the true value of your statistical estimate because it is based on a sample, not on the whole population.

The confidence interval only tells you what range of values you can expect to find if you re-do your sampling or run your experiment again in the exact same way.

The more accurate your sampling plan, or the more realistic your experiment, the greater the chance that your confidence interval includes the true value of your estimate. But this accuracy is determined by your research methods, not by the statistics you do after you have collected the data!

## Hypothesis Testing

We are being faced with the need to make decisions about how best to analyse massive datasets. We want to help users make decisions when looking at data. Sometimes though it’s too expensive to check all the data or it’s so complicated that it's easy to make an incorrect assumption and be led away in the wrong direction.

In cases like this, hypothesis testing can help by providing a degree of confidence that either our observations are real, or the changes we’ve made have, in fact, made a difference.

In cases where a complete examination of the underlying data set is impossible - perhaps all the data is not yet available or is simply too expensive to process all of it - we have found the following statistical tests to be very helpful.

#### **Hypothesis testing** is a statistical method that can be used to make decisions about a data set without having to examine every element in that dataset. For example, imagine you have a software system that processes billions of events per hour. Events are grouped into transactions of, say, hundreds of events. Your product owner has identified a candidate product feature that could provide real customer value but only if at least 80% of the transactions over the last 12 months contain events that match a given set of criteria (profile).

Now we have a problem. It will take weeks to check to process 12 months of events.

Why are we bothering to take a sample? Because we want to make a decision, and checking every element in the set might be too difficult (billions of events), or just impossible (testing food means destroying it).

The issues then become:

+ There is something we want to know about the entire population, but we can’t interrogate all of it.
+ We sample the population and learn something about that sample, but since it’s only a sample, we can’t be sure that it is, in fact, representative of the entire population.
+ Finally, what - if anything - can we guess about the population, given what we’ve learnt about the sample?
+ This can all get very heavy, very quickly, so I’ll give a quick example of what a hypothesis test does. In this example we have a data set that’s so large we can't process all of it to get an answer, so we have to sample it, and then check what conclusions we can deduce from this sample.

**Example:**

+ Suppose your software application is processing billions of transactions per hour.
+ Your product owner has asked you to implement some new way to process these transactions, but it’s only a worthwhile feature to implement if at least 80% of the transactions - over the whole of the last year - match a given profile.
+ Now suppose that a check to see if a given transaction fits this profile was so expensive to calculate that it would take weeks to check all of them.
+ So, instead, you sample just 1,000 transactions and find out that 82% of the sampled transactions have the required profile.

#### What can we say about all these billions of transactions, given what we have learnt about just this sample of 1,000? This is where the null hypothesis and alternative hypothesis come into play.

### Null and Alternative Hypothesis
A hypothesis test starts with making two hypotheses

+ **The null hypothesis** - in general, this is a “suppose there’s nothing to see here” case.
+ **The alternative hypothesis** - this is what we’re checking for.

The test works by assuming the null hypothesis is true and then checking to see how likely a sample fits into that hypothesis. If it’s not likely enough, then we can suggest the alternative hypothesis is true.

Before taking the sample a significance level is selected. By convention this is 5% - but be advised, this is only a convention, and you must choose this with care. Later on, you will be making a judgement based on a derived probability by comparing it to this significance, so it’s important to consider the significance level before taking the sample.

Technically, this makes this kind of hypothesis test a significance test - we’re not proving anything. We are only deciding that, on the balance of probabilities, given how much risk we’re willing to take, that we’re happy to accept that something is likely enough to be true.

Does that sound vague? It should. There are reasons to be very careful about the kinds of assumptions you should be willing to make based on the results of these tests.

In short, these tests aren’t about certainty, they’re about confidence.

In our example, we would start by assuming this null hypothesis is true:

#### **`Exactly 80% of the transactions match the profile`**

What we want to do now is imagine the following. Note, we don’t actually have to do the following, this is just here to explain to you why this all works.

![image](https://user-images.githubusercontent.com/99672298/200489836-74cf2ba7-f984-4c99-8acf-b938247ab712.png)

+ **Imagine what would happen if we were to take lots of samples from a population where the proportion was exactly 80%**
+ **Each sample we took would have a different proportion; but we'd expect most of them to be near enough to the "real" one of 80%**
+ **If we count how many of each proportion we get, the result is a histogram where the "real" proportion has the highest bar.**
+ **Eventually, if we were to take more and more samples, this would tend towards a normal curve, centred around 80%**

Now we have a curve - for a fictional population that matches our null hypothesis - with which we can compare our sample.

#### Sample and Compare to Null Hypothesis
So, how do we check our sample against this null hypothesis curve? First, we define our alternative hypothesis - i.e. this is the thing we’re trying to prove. For the kinds of tests we’re talking about here, this must be related to the null hypothesis - i.e. it must be comparing the same terms, just comparing them with a different operator.

+ In our example, because we have the null hypothesis:

  + Exactly 80% of the transactions match the profile

+ We would consider this as our alternative hypothesis:

  + More than 80% of the transactions match the profile

Finally, we compare our sample proportion (in our example this was 82%) to the curve for the null hypothesis, and we figure out how likely it is that this sample could have come from a population where the proportion was, in fact, exactly 80%.

![image](https://user-images.githubusercontent.com/99672298/200493873-44660677-b16a-4abc-90e9-0fca492d9c7b.png)

In our example, since we’re checking how likely it is that our real population proportion is greater than 80% (our assumed null hypothesis population proportion), we are, in effect, comparing:

+ The area under this curve to the right of where our sample result is.
+ To the total area under this curve.

This fraction is the probability of how likely it is that our sample came from a population that had a proportion that matched our null hypothesis.

**Drawing conclusions about the sample**
All of the tests that follow derive a result called a p-value. These values are often misunderstood. This misunderstanding can lead the tester to make certain assumptions about the underlying population that cannot be justified.

The p-value is the probability that the sample result could have occurred if the null hypothesis were true.

So, a p-value has no meaning outside of the given sample, and cannot be related to any other sample or p-value, and doesn't give an indication of how accurate the sample value is. So, in our example, had we calculated a p-value of 4%, the following significance levels would have caused us to draw the following conclusions:

#### Significance	                

**5%**

#### Conclusions

The p-value of 4% is less than the significance of 5%.

So, the probability of this sample coming from a population with the values assumed by the null hypothesis is not significant.
                              
So, we can reject the null hypothesis, which suggests the alternative hypothesis. NOTE: this doesn’t prove the alternative hypothesis; only that we can feel a degree of confidence that more than 80% of the transactions match our profile.
                              
We cannot say anything else about the actual value of the proportion of the underlying population - i.e. we can’t say that it’s likely to be 82%, or even close to 82%


![02 03 2022_14 50 41_REC](https://user-images.githubusercontent.com/99672298/200490854-e2e48e78-76a9-4e63-a96d-b999d37abd72.png)
![02 03 2022_14 51 55_REC](https://user-images.githubusercontent.com/99672298/200490895-cf18c898-5ba7-478a-b8e1-bdd4b30b82ff.png)
![02 03 2022_14 52 34_REC](https://user-images.githubusercontent.com/99672298/200490910-b56d2d94-112f-4d45-b9c6-332085b7f862.png)
![02 03 2022_14 53 24_REC](https://user-images.githubusercontent.com/99672298/200490956-7a2196e2-37ae-43da-9535-4ee4be77cfb7.png)

### 1-Sample Z-Test
VisiMetrix monitors large telecom networks, and in some cases its data will suggest that new software or hardware elements should be added to the network to improve overall performance. Since changing telecom networks is costly, we need to determine whether this change would be worthwhile by verifying that a sizeable proportion of the underlying traffic matches a well-defined profile. Unfortunately, checking such vast quantities of data is extremely compute and time-intensive.

In cases like this, a test known as the 1-sample Z-test can be applied to a sample of the data to determine if the network infrastructure change is, in fact, worthwhile implementing.

![image](https://user-images.githubusercontent.com/99672298/200487694-2f944459-16ed-4f84-b45b-8ab70afd16a6.png)

### 2-Sample Paired T-Test
When VisiMetrix draws the attention of a telco’s operations team to a history of PDP creation (user connectivity) errors, they will often apply a configuration change to their underlying network to correct this. However, since things like PDP creation errors are, for the most part, rare, it can be a challenge to validate that a configuration change has, in fact, corrected connection failures for real end-customers.

In cases like this, a 2-sample paired t-test can be applied to samples taken before and after the configuration changes to confirm that any reduction in errors was, in fact, real, and not just a random artifact of the data.

![image](https://user-images.githubusercontent.com/99672298/200487723-8c110d62-cf6a-45c0-9f10-59e81316daae.png)

![image](https://user-images.githubusercontent.com/99672298/200488088-a4b1c629-c68d-4010-9ded-9891d7107dce.png)
![image](https://user-images.githubusercontent.com/99672298/200488125-be05c18a-e51a-4394-9284-4f0dca4fce1a.png)
![03 02 2022_19 42 46_REC](https://user-images.githubusercontent.com/99672298/200491133-94fa2d06-9701-4407-9692-cfb6476bb26a.png)



![02 03 2022_15 55 54_REC](https://user-images.githubusercontent.com/99672298/200491104-57025f8b-dc6b-4e99-ad3d-412da0bb203a.png)
![02 02 2022_11 07 08_REC](https://user-images.githubusercontent.com/99672298/200490594-343565e2-0e54-436a-86a2-5b259c92b6a5.png)
![09 03 2022_19 04 52_REC](https://user-images.githubusercontent.com/99672298/200491926-8315e10a-35fa-44ee-8230-c62c4a385acd.png)
![09 03 2022_15 21 32_REC](https://user-images.githubusercontent.com/99672298/200491788-5648d8db-f662-4af9-9758-0d24437a5ea8.png)
![01 02 2022_16 41 36_REC](https://user-images.githubusercontent.com/99672298/200490412-81ca94b3-2bff-4679-b4eb-3d677cf6554d.png)
![image](https://user-images.githubusercontent.com/99672298/200490042-1b14a8cf-c47e-4641-9a72-1d84c33b0a94.png)
![04 02 2022_11 17 15_REC](https://user-images.githubusercontent.com/99672298/200491460-c7149ece-c29a-4362-bbb2-f914306022d9.png)

## Questions for Hypothesis Testing:

![image](https://user-images.githubusercontent.com/99672298/160234770-3fa8fc97-a0ec-41a3-85a4-e10bcd7283bf.png)
![image](https://user-images.githubusercontent.com/99672298/160234786-d9414132-f471-4f9e-b421-4bcbfc1880a9.png)



### Q.A cartwheeling competition was organized for some adults. The data looks like following

(80.57, 98.96, 85.28, 83.83, 69.94, 89.59, 91.09, 66.25, 91.21, 82.7 , 73.54, 81.99, 54.01, 82.89, 75.88, 98.32,107.2 , 85.53, 79.08, 84.3 , 89.32, 86.35, 78.98, 92.26, 87.01)

Is the average cartwheel distance (in inches) for adults more than 80 inches?

Null Hypothesis: 𝜇 = 80

Alternative Hypthosis: 𝜇 > 

![image](https://user-images.githubusercontent.com/99672298/160234803-cb4a3457-f128-4c83-b445-bdb95abb066a.png)

### Q.You want to test an American citizen's claim that the average height of an American is 175.3 cm. Measure the heights of ten American males and use the T-test to determine if the American’s claim is true.

Null Hypothesis: 𝜇1 = 175

Alternative Hypthosis: 𝜇1≠ 175

### Q.Question

In previous years, 52% of parents believed that electronics and social media was the cause of their teenager’s lack of sleep. Do more parents today believe that their teenager’s lack of sleep is caused due to electronics and social media?

### Q.Question

Considering adults in the NHANES data, do males have a significantly different from the mean Body Mass Index of females?

Null Hypothesis: 𝜇1=𝜇2

Alternative Hypthosis: 𝜇1≠𝜇2

![image](https://user-images.githubusercontent.com/99672298/160234815-784c443b-4c64-458f-8f56-d74627bbf476.png)

![image](https://user-images.githubusercontent.com/99672298/160234821-d60bd579-475f-4875-8a01-c7c1ac105423.png)

### Q.Research Question

Is there a significant difference between the population proportions of parents of black children and parents of Hispanic children who report that their child has had some swimming lessons? Data: 247 Parents of Black Children. 36.8% of parents report that their child has had some swimming lessons. 308 Parents of Hispanic Children. 38.9% of parents report that their child has had some swimming lessons.

**Null Hypothesis:** p1 - p2 = 0

**Alternative Hypthosis:** p1 - p2 ≠ 0

![image](https://user-images.githubusercontent.com/99672298/160234831-956d7700-261d-4468-b4f2-ef09f9a03455.png)

![image](https://user-images.githubusercontent.com/99672298/160234836-d74d2955-1b4d-4ef6-98e6-6a22bee51166.png)

### Q.Chi Square - Goodness of Fit

A shop owner claims that an equal number of customers come into his shop each weekday. To test this hypothesis, a researcher records the number of customers that come into the shop in a given week and finds the following:

+ Monday: 50 customers
+ Tuesday: 60 customers
+ Wednesday: 40 customers
+ Thursday: 47 customers
+ Friday: 53 customers

**Null Hypothesis:** There is no significant difference between the observed and the expected values.

**Alternate Hypothesis:** There is a significant difference between the observed and the expected values.

![image](https://user-images.githubusercontent.com/99672298/200488167-39a2d405-c29c-4134-9156-888b71e79560.png)

![01 02 2022_16 22 44_REC](https://user-images.githubusercontent.com/99672298/200490154-f7f6e1b9-24c5-4158-823d-502290c01048.png)
![01 02 2022_10 33 37_REC](https://user-images.githubusercontent.com/99672298/200490357-f1efbb0c-5942-4e10-ae97-604be80de042.png)
![01 02 2022_16 42 13_REC](https://user-images.githubusercontent.com/99672298/200490437-b5d10980-784e-4601-98fb-fefe6f4ea90b.png)
![01 02 2022_16 43 48_REC](https://user-images.githubusercontent.com/99672298/200490470-bbe81c70-1055-4cce-a7c5-1964acd6f82a.png)
![01 02 2022_16 44 47_REC](https://user-images.githubusercontent.com/99672298/200490478-d16a250c-f41e-441f-8427-57aebb447ac3.png)
![01 02 2022_16 46 42_REC](https://user-images.githubusercontent.com/99672298/200490499-50667126-b240-412f-9a3e-a1ecb10af310.png)
![02 02 2022_15 03 25_REC](https://user-images.githubusercontent.com/99672298/200490738-f10320fb-ed73-422c-9ee7-b3eba4cdd1df.png)
![03 02 2022_19 38 15_REC](https://user-images.githubusercontent.com/99672298/200491036-6acaad67-c045-4594-9b08-7604946dce32.png)
![03 02 2022_19 58 46_REC](https://user-images.githubusercontent.com/99672298/200491301-6af0cf8c-2dab-4b9f-a8e9-5d254bddef40.png)
![03 02 2022_20 05 32_REC](https://user-images.githubusercontent.com/99672298/200491347-2be79585-9dc2-4d69-8daf-38b616577930.png)
![03 02 2022_20 02 26_REC](https://user-images.githubusercontent.com/99672298/200491363-642e5582-f762-41be-89e5-097456cd4fd8.png)
![03 02 2022_20 04 18_REC](https://user-images.githubusercontent.com/99672298/200491369-44b26e22-7b81-4e54-ab97-77c6530619a0.png)
![04 02 2022_10 41 09_REC](https://user-images.githubusercontent.com/99672298/200491416-c10848b6-db0a-4b51-abc4-3ee5660cedc3.png)
![08 03 2022_22 59 28_REC](https://user-images.githubusercontent.com/99672298/200491736-053f1d08-66fb-4450-9330-a5217e8cd1e7.png)



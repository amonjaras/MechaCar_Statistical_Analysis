# **MechaCar Statistical Analysis**
R

## **INDEX**

- [Deliverable 1](#deliverable-1-linear-regression-to-predict-mpg)

- [Deliverable 2](#deliverable-2-summary-statistics-on-suspension-coils)

- [Deliverable 3](#deliverable-3-t--tests-on-suspension-coils)

- [Deliverable 4](#deliverable-4-study-design-mechacar-vs-competition)


## **Deliverable 1: Linear Regression to Predict MPG**

1. **Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?**

At a confidence level of 95%, the significance level is 0.05. In order for the p-value to be statistically significant,  should be less than 0.05

As a result, the variables or coefficients that provides a non-random amount of variance to the mpg values are:

vehicle length(Pr(>|t|)=2.60e-12),ground - clearance(Pr(>|t|)=5.21e-08)

and

intercept(Pr(>|t|) = 5.08e-08)

This indicates that vehicle length and ground clearance have statistically significant impact on fuel efficiency(mpg). Also, the intercept is statistically significant, meaning there are other variables or factors that may contribute to the variation in mpg values but are not included in the linear model.

2. **Is the slope of the linear model considered to be zero? Why or why not?**

In case of linear regression analysis;

- H0 : The slope of the linear model is zero

- Ha: The slope of the linear model is not zero

In this case, our p-value is less than our assumed significance level of 0.05

- p-value = 5.35e-11

- p-value < 0.05

Therefore, we reject the null hypothesis, which means that the slope of the linear model is not zero.

3. **Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?**

The r2 value in this case is 0.7149, which means that this linear model can predict approx 71% of mpg values of Mechacar prototypes.

All values can be verified on Figure 1

> *Fig 1: Linear model*

![Deliverable1](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv1.png)

[:top: Go To Top](#index)

## **Deliverable 2: Summary Statistics on Suspension Coils**

1. **The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?**

- In our total_summary dataframe, we can see that the variance for manufacturing lots in total is 62.29 which is less than 100 PSI. Therefore it meets the design specification. See Figure 2

> *Fig 2: total_summary dataframe*

![Deliverable2a](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv2_1.png)

- In our lot_summary dataframe, we can see that the variance for Lot 1 is 1(approx) and lot 2 is 7(approx). Therefore, they are within the design specification limit of 100 PSI. However, the variance for Lot 3 is 170 which is much higher than the design specification limit of 100 PSI. See Figure 3

> *Fig 3: lot_summary dataframe*

![Deliverable2b](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv2_2.png)

[:top: Go To Top](#index)

## **Deliverable 3: T-Tests on Suspension Coils**

1. **Determine if the PSI across all manufacturing lots is statistically different from the population mean of 1,500 pounds per square inch.**

- The t-test for all manufacturing lots show a p-value of **0.06028** which is higher than our assumed significance level of 0.05.
Meaning, we fail to reject null hypothesis, since the PSI across all manufacturing lots is not statistically different from the presumed population mean of 1500. See Figure 4

> *Fig 4: t-test for all manufacturing*

![Deliverable3a](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv3_1.png)

2. **Determine if the PSI across manufacturing lot1 is statistically different from the population mean of 1,500 pounds per square inch.**

- The t-test for manufacturing **lot1** shows a p-value of 1 which is higher than our assumed significance level of 0.05.
We fail to reject null hypothesis, which means that the PSI mean across manufacturing lot 1 is not statistically different from the presumed population mean of 1500. See figure 5

> *Fig 5: t-test for lot1*

![Deliverable3b](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv3_2.png)

3. **Determine if the PSI across manufacturing lot2 is statistically different from the population mean of 1,500 pounds per square inch.**

- The t-Test for manufacturing **lot2** shows a p-value of 0.6072 which is again higher than our significance level of 0.05.
We fail to reject the null hypothesis, which means that there is no statistical difference between sample PSI mean and population mean of 1500. See Figure 6

> *Fig 6: t-test for lot2*

![Deliverable3c](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv3_3.png)

4. **Determine if the PSI across manufacturing lot3 is statistically different from the population mean of 1,500 pounds per square inch.**

- The t-test for manufacturing **lot3** shows a p-value of 0.04168 which is lower than our significance level of 0.05.
We reject the null hypothesis, meaning that there is a statistically significant difference between the lot 3 mean and the population mean of 1500. See Figure 7

> *Fig 7_ t-test for lot3*

![Deliverable3d](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv3_4.png)

In conclussion something has gone wrong with Manufacturing Lot 3 causing problems with the production. The company needs to inspect the suspension coils from Manufacturing Lot 3.

[:top: Go To Top](#index)

## **Deliverable 4: Study Design: MechaCar vs Competition**

1. **What metric or metrics are you going to test?**

- The goal is to design a statistical study to improve vehicle performance of the MechaCar vehicles vs vehicles by other manufacturing companies. Although there are many, one important metric that it might interest consumers and motivate them to buy from Mechacar instead of other manufacturers is the Resale Value.

2. **What is the null hypothesis or alternative hypothesis?**

- **H0**: There is no statistically significant difference between resale value mean of MechaCar vehicles and other competitors

- **Ha**: There is a statistically significant difference between the resale value mean of MechaCar vehicles and other competitors

3. **What statistical test would you use to test the hypothesis? And why?
What data is needed to run the statistical test?**

- To test the hypothesis mentioned above, it is needed to conduct a one-way ANOVA test. A one-way ANOVA(Analysis of Variance) is used to test the means of a single dependent variable across a single independent variable with multiple groups. It will allow us to compare the resale value of MechaCar vehicles with several other competitors.

- Our dependent variable would be the Resale Value which is numerical and continuous; the independent variable could be vehicle class which is categorical. We also need to validate that the dependent variable is normally distributed and that the variance among each group is similar. In R, we can use the aov() function along with the summary() function to conduct the the ANOVA test. If the Pr(>F) value is greater than our assumed significance level of 0.05 at 95% confidence level, we can conclude that there is no statistically significant difference between the means of the groups. Otherwise, we will know that at least one of the means is different from all other groups which would then require us to conduct further tests.


[:top: Go To Top](#index)

This work belongs to [^1].
Course [^2].
[^note]:
[^1]: Author: Audrey MONJARAS :mexico: :canada:
[^2]: Data Analytics: Unit 14 Data Visualizations with Tableau and Pandas

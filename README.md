# **MechaCar Statistical Analysis**
R

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

## **Deliverable 2: Summary Statistics on Suspension Coils**

1. **The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?**

- In our total_summary dataframe, we can see that the variance for manufacturing lots in total is 62.29 which is less than 100 PSI. Therefore it meets the design specification. See Figure 2

> *Fig 2: total_summary dataframe*

![Deliverable2a](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv2_1.png)

- In our lot_summary dataframe, we can see that the variance for Lot 1 is 1(approx) and lot 2 is 7(approx). Therefore, they are within the design specification limit of 100 PSI. However, the variance for Lot 3 is 170 which is much higher than the design specification limit of 100 PSI. See Figure 3

> *Fig 3: lot_summary dataframe*

![Deliverable2b](https://github.com/amonjaras/MechaCar_Statistical_Analysis/blob/main/Images/deliv2_2.png)

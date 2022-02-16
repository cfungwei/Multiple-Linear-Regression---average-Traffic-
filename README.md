# Multiple-Linear-Regression---average-Traffic

The dataset presents us with 121 observations, 4 predictor variables and 1 response variables. 

1.  Y - Average annual daily traffic (aadt) (Response Variable)
2. X1 - Population of county in which road section is located
3. X2 - Number of lanes in road section
4. X3 - Width of road section (ft)
5. X4 - Two-category quality variable indicating whether or not there is control of access to road section

Data had no missing values and target variables were already isolated. We proceed with a scatter plot matrix to identify a correlation between variables but the plot below seems to no have any observable pattern. *Looking back, using a scatter plot on categorical data might not be as effective as using a boxplot on each level of the factor. This can help us visualize if there is a direct correlation between the levels and increasing aadt. An increase in the quartiles and median would convince me of an existing correlation*

<img width="480" alt="Scatterplotmatrix" src="https://user-images.githubusercontent.com/97843966/154043849-64ba411c-baf3-4740-b7d6-881b872d868a.png">

Modelling and Adequacy Testing
---
Multiple Adequacy testing will be used: F-test, t-test, R<sup>2</sup> statistic, residual plots, normality checking (non-constant variances and higher order curvatures) ([QQ-plot](https://towardsdatascience.com/q-q-plots-explained-5aa8495426c0)) and sequential checking ([durbin-watson](https://en.wikipedia.org/wiki/Durbin%E2%80%93Watson_statistic))

To see the entire process, the [code](https://github.com/fungiiiii/Multiple-Linear-Regression---average-Traffic-/blob/main/main) can be accessed here.Our final model will be y<sup>λ</sup> = X1 + X2 + X1X2 + X1X4

<img width="480" alt="Summary" src="https://user-images.githubusercontent.com/97843966/154052057-cdc79afd-f077-4a73-8f63-deffc915aa94.png">

Above are the results for the F-test, T-test and R<sup>2</sup> statistic where we find that we reject the null hypothesis for both test and find that both model and variables are significant. Furhtermore, R<sup>2</sup> statistic is at 0.8614 which implies the model fits the train set well. 

<img width="480" alt="Normality" src="https://user-images.githubusercontent.com/97843966/154052064-96a7010d-31c0-4e8c-89e7-029ed5c435ec.png">

From the above array of plots, the variance for residual plots seem to show no patterns and residual plots have a constant variance. QQ plot identifies the normality of the model and the plot indicates that the model likely follows a normal plot with little skew.

<img width="480" alt="Durbin Watson" src="https://user-images.githubusercontent.com/97843966/154052211-d2dedd07-8d67-4581-bd15-2d40bee332e4.png">

Image above shows that the durbin-watson p-value is at 0.04912. We would be required to reduce our significance level from 0.99 to 0.95 such that it will not reject the model that it is sequentially correlated. 

---

In conclusion, our final model fits the best compared to the previous models to predict the annual average daily traffic.

*Done on Nov 2021
Credits: Ang Kian Hao, Julianne Thatcher Low, Seng Swee Keng, Wisely Neo*

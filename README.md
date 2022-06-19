# MechaCar_Statistical_Analysis

##Overview
AutoRU has asked us to use our data analytics skills to evaluate 50 different vehicle prototypes' expected Miles Per Gallon (MPG) based on a variety of design characteristics. We will accomplish this task by performing multiple linear regression analysis based on the variables assosiated with high and low MPG in vechiels already in the MechaCar csv provided. This will provide AutoRU insight into expected MPG for the new prototypes.

## Linear Regression to Predict MPG!

![Deliverable #1, Mod_15](https://user-images.githubusercontent.com/100163289/174489646-6a5f5108-62c1-4ed4-821d-ac75fcbad35b.png)

### Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
Any variable that delivers a Pr(>|t|) of .05 or less will have a significant amount of variance (or non-random amount of variance) with MPG. Conversely, any variable above .05 will have less variance (or random amount of variance) with MPG. Out of our six variables, car length (2.60e-12) and vehicle height (5.21e-08) had the greatest amount of non-random variance with estimated MPG. This is not super surprising as both variables are highly correlated with trucks or SUVs which will have lower MPG. The variables least correlated with MPG are spoiler angle and AWD as their Pr(>|t|) is much larger than .05.

### Is the slope of the linear model considered to be zero? Why or why not?
No, our analysis shows that some variables (vehicle ground clearance and length) had a significant impact on vehicles' MPG.

### Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?
The linear model is estimated to predict the prototypes' MPG accurately 71.49% of the time based on the multiple R-Squared calculation and 68.25% of the time on the adjusted R-Squared calculation. Whether a model that predicts the outcome 71% of the time is effective or not might be subjective, but in this situation, I would think it would be sufficiently accurate as it provides AutoRU a good starting point in evaluating the MPG of MechaCar's prototypes.

## Deliverable #2
### The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

### Total Summary Dataframe
![total_summary_df](https://user-images.githubusercontent.com/100163289/174489796-488fda11-d755-48a8-a077-b3f22efaa15b.png)

MechaCar dictates a tolerance for their suspension springs not exceed 100 pounds per square inch. Based on the information provided, the manufacturing data indicates the springs are within tolerance with a variance of 62.29 pounds per square inch.
 

### Lot Summary Dataframe
![lot_summary_df](https://user-images.githubusercontent.com/100163289/174489799-4a6f82e0-548a-437e-8082-ab22a1c2b25a.png)

The Lot Summary Data frame provides some very worrying information as it shows lot 3's tolerance well exceeds MechCar's requirements at 170.28 pounds per square inch. This is a good example of the law of averages and the importance of quality control in the manufacturing process. In this instance, MechaCar should reject the coil springs from lot 3.




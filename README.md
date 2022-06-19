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

## Summary Statistics on Suspension Coils

### The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

### Total Summary Dataframe
![total_summary_df](https://user-images.githubusercontent.com/100163289/174489796-488fda11-d755-48a8-a077-b3f22efaa15b.png)

MechaCar dictates a tolerance for their suspension springs not exceed 100 pounds per square inch. Based on the information provided, the manufacturing data indicates the springs are within tolerance with a variance of 62.29 pounds per square inch.
 

### Lot Summary Dataframe
![lot_summary_df](https://user-images.githubusercontent.com/100163289/174489799-4a6f82e0-548a-437e-8082-ab22a1c2b25a.png)

The Lot Summary Data frame provides some very worrying information as it shows lot 3's tolerance well exceeds MechCar's requirements at 170.28 pounds per square inch. This is a good example of the law of averages and the importance of quality control in the manufacturing process. In this instance, MechaCar should reject the coil springs from lot 3.

## T-Tests on Suspension Coils
For Deliverable # 3, we wrote a t.test function to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.

### Combined T-test
![T-test (all)](https://user-images.githubusercontent.com/100163289/174496128-5aa49a19-cc15-4d6b-b594-3612c706b1ee.png)

The return of the combined T-test of t = -1.8931 shows the population is statistically different from the population mean. The combined T-test provides a p-value of .06028, which is larger than .05 and therefore rules out being able to reject our null hypothesis.

### T-test (Lot 1)
![T-test (lot 1)](https://user-images.githubusercontent.com/100163289/174496146-769235c0-e14e-4a77-8c67-a59b628d9b6f.png)

The return of the Lot 1's T-test of t = 0 shows the population is not statistically different from the population mean. The T-test for lot 1 returns a p-value of 1, which is significantly more than .05 and results in our inability to reject the null hypotheses.


### T-test (Lot 2)
![T-test (lot 2)](https://user-images.githubusercontent.com/100163289/174496148-0de69b5f-7d8c-4372-b1c4-c0258faa95d7.png)

The return of the Lot 2's T-test of t = .51745 shows the population is statistically different from the population mean. The T-test for lot 2 returns a p-value of .6072, which is more than .05 and results in our inability to reject the null hypotheses.

### T-test (Lot 3)
![T-test (lot 3)](https://user-images.githubusercontent.com/100163289/174496151-3183cf1a-d9be-48c0-aead-60a98b9d8889.png)

The return of the Lot 3's T-test of t = -2.0916 shows the population is statistically different from the population mean. The T-test for lot 3 returns a p-value of .04168, which is less than .05 and allows us to reject our null hypothesis. Once again, lot 3 proves to be an outlier from the remainder of the lots and should be investigated further.
 
## Study Design: MechaCar vs Competition

### Study Design

When designing a statistical study to compare performance of MechaCar against the performance of vehicles of other manufactures, it will be important to measure similar and relevant data. For example, vehicle weight, vehicle length, and ground clearance are all good metrics to compare as they are highly correlated with a critical factor (MPG). Spoiler angle and AWD might not be relevant to MPG as they are not very correlated in our linear regression model. This is why figuring out what to measure might be just as important on how you measure it. 

For a statistical study, I would want to limit the analysis to six metrics that would allow for a relevant head-to-head comparison between MechaCar and its competitors. I would also limit the analysis to a particular category of vehicle (truck, suv, sedan, sports car, etc) as this will keep the analysis focused and its output more relevant. 

I would use vehicle weight, MPG (city), MPG (highway), horsepower, safety rating, and ground clearance for my analysis as each of these are quantifiable, comparable, and easily available in marketing material. I would also run a separate analysis for sports cars, suvs/trucks, and sedans. Additionally, I might also run the same analysis limited to hybrid and/or electric vehicles if enough of the manufactures are selling hybrid and/or electric vehicles in large enough quantities and/or MechaCar is manufacturing such cars. 

### Hypotheses

Null Hypothesis: MechaCar has a better power-to-weight ratio than its competitors. 
Alternative Hypothesis: MechaCar does not have a better power-to-weight ratio than its competitors. 

### Statistical Test and Dataset

I would use a T-test model to test the statistical difference between the power (horsepower) and weight of the various vehicles using a randomized group of competitors and MechaCar’s models. 


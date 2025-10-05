

HEART DISEASE  
*FINAL COURSE PROJECT*  
STATISTICAL MODELS AND STOCHASTIC PROCESSES   
                         Ainhoa López Carrasco

					

***1.Introduction***

What is heart disease? Also known as CVD, this term refers to several type of heart conditions with examples such as high blood pressure, stroke or vascular dementia, all of which have negative effects on heart health and blood circulation.1

CVD remains as the leading cause of global mortality, representing 31% of all deaths worldwide, with approximately 18 million deaths per year. The main cause of CVD is the obstruction caused by the accumulation of fatty deposits on the inner walls of blood vessels, preventing regular blood flow to the heart or brain. We have to be aware of this issue because heart problems can affect everyone around the world.3

We need pathological and clinical information in order to perform reliable diagnoses, and that’s why our goal for this project is to forecast the significant predictors to construct the most effective model.

***1.2. Techniques*** 

**Logistic Regression analysis and Maximum Likelihood Estimation (MLE)**     
	 	 	 		  
We’re using Logistic Regression and Maximum Likelihood Estimation to study our dataset. The patients are labeled with 1 for dying due to a condition of heart disease and 0 for surviving. Logistic regression will help us understand how the variables are connected and predict if someone has died due to that predictor. Maximum Likelihood Estimation estimates the model parameters by maximizing the likelihood function, and we will use it to contrast the efficiency of the logistic regression analysis. To make sure we are using the best possible models, we will also require likelihood ratio tests, such as ANOVA tests.

***2\. Dataset***   
This dataset was obtained from  the UC Irvine Machine Learning Repository.2

* It contains 13 features which its data is obtained from different observations on 299 patients:

| Feature | Type | Description | Units/Values |
| :---- | :---- | :---- | :---- |
| Age | Integer | Age of the patient | Years |
| Anemia | Binary | Decrease of red blood cells or hemoglobin | 0 \= False 1 \= True |
| Creatinine Phosphokinase | Integer | Level of the CPK enzyme in the blood | mcg/L |
| Diabetes | Binary | If the patient has diabetes | 0 \= False 1 \= True |
| Ejection fraction | Integer | Percentage of blood leaving the heart at each contraction | % |
| High blood pressure | Binary | If the patient has hypertension | 0 \= False 1 \= True |
| Platelets | Continuous | Platelets in the blood | kilo platelets/mL |
| Serum Creatinine | Continuous | Level of serum creatinine in the blood | mg/dL |
| Serum Sodium | Integer | Level of serum sodium in the blood | mEq/L |
| Sex | Binary | Woman or man  | 0 \= Woman 1 \= Man |
| Smoking | Binary | If the patient smokes or not | 0 \= False 1 \= True |
| Time | Integer | Follow-up period | Days |
| Death Event | Binary | If the patient died during the follow-up period | 0 \= False 1 \= True |

***3\. Data Analysis***   
We will check each predictor individually. Then, our goal will be to construct a model that uses many predictors, aiming to predict the probability of experiencing death due to heart disease.

**Age**  
When we think of heart diseases, what comes to mind first is an image of elderly people. But is this common thought true? We were determined to prove it statistically:

What this histogram is showing is a bar for each age group. The part covered in red means that they survived, and the part covered in blue means that they perished. The size of the bar is linked to the count for each age group, meaning that the tallest bars are the ones with the highest number of people. By only looking at the plot we can observe that as older the people get, the lower the probability of survival is and by recognizing this pattern we expect a relationship between the variables “age” and “DEATH\_EVENT”. *FIGURE 1*

That’s why we performed a logistic regression test, to confirm the relationship we expect.

Since the p-value is statistically significant for α \= 0.05, we have a clear indication that the predictor “age” is significant. We also computed the confidence interval for 95% confidence to double-check the significance and we can confirm that since the CI does not include 0, the significance is not due to random chance and does in fact have a relationship with the response variable. We also compared the estimated coefficients of the logistic regression by computing the MLE parameters in R and we obtained the same coefficients thus meaning the approach we took is correct and ratifies the relationship between the variables.*FIGURE 2* 

To visualize the relationship, we’ve computed a plot with a logistic regression curve, plotted some data points and created a decision boundary striped line to determine if the predictor is significant. As we can clearly see, the huge steeps the curve takes confirms the significance of the predictor “age”.*FIGURE 3*

**Anemia**  
Anemia is a condition in which the body does not produce the necessary amount of healthy red blood cells. This lack of oxygen might make you feel weaker or tired4. We wanted to check if having anemia was a significant predictor by statistical analysis:

The data in this plot is in binary format, value 0 meaning that they do not have the condition and value 1 meaning that they do. The color scheme applies the same as the last plot, red being survival and blue being death. We can observe that the red color is prominent when compared to the blue one, thus we can predict that anemia will not be a significant predictor of heart disease since there is no clear relationship between the predictor “anemia” and the response variable “DEATH\_EVENT”.*FIGURE 4*

When we performed logistic regression analysis on the “anemia” predictor, we found that the p-value is not statistically significant for ɑ \= 0.05, so we can not reject the null hypothesis and conclude that the predictor does not have a significant relationship with the response variable “DEATH\_EVENT”. Moreover, we can clearly see that in the 95% confidence interval we computed that it includes the value 0, so keeping in mind the obtained p-value, there is no true effect in the population and any observed variation in the sample could be explained by random chance. When computing the MLE parameters we obtain, yet again, the same estimated coefficients as in logistic regression *FIGURE 5*. 

In the following plot, we can see that the peaks in the logistic regression curve tend to lower values of the death event, thus confirming the non-significance of the predictor. This can also be interpreted as a gradually changing logistic regression curve, which endorses that the predictor does not significantly influence the probability of the positive outcome, in this case, having a relationship with “DEATH\_EVENT”. The peaks we observe indicate points where the probability is relatively higher, this being caused by a wide confidence interval and creating uncertainty about the impact.*FIGURE 6*

**Creatine Phosphokinase**  
Creatine Phosphokinase (also known as CPK) is an enzyme in the body found mainly in the heart, brain and skeletal muscle. When the total CPK level is extremely high, it often means that there’s been an injury or stress on muscle tissue, the heart or the brain. When a muscular organ such as the heart is damaged, CPK leaks into the bloodstream.5

In our data set, the variable was called “creatinine\_phosphokinase”, so we will be referring to CPK as such on any occasion that CPK appears on the R file. In the following plot we observe that when having lower concentrations of CPK the DEATH\_EVENT is unlikely when compared to the other extrema, this being high concentrations of CPK which leads to no survival cases.*FIGURE 7*  
 This indicates a possible relationship between the variables, but to confirm it we will perform a logistic regression analysis. This analysis shows us that although the relationship might seem clear by only looking at the plot, the reality is far from what we expected since the p-value is not significant for ɑ \= 0.05. Moreover, when we compute the confidence interval for 95% confidence we can clearly see that the value 0 is inside the interval. This suggests that there’s a chance that the effect on the population is random and not due to the significance of the predictor. We confirm that our model has been built correctly because                                                                                                            the MLE parameters coincide with the estimated coefficients in the logistic regression. *FIGURE 8*

What we can determine from the plot below is that although the DEATH\_EVENT is unlikely to occur, it is not impossible due to the increase of the peaks in the logistic regression curve. We can see that the curve starts with its highest peak just at the decision boundary striped green line, but when increasing the CPK concentration, the death event is slowly increasing. This might be due to random chance, but also due to correlation between predictors.*FIGURE 9*

**Diabetes**  
Diabetes is a chronic metabolic disease which is characterized by the high levels of blood glucose (also known as blood sugar) which if not treated inevitably leads to detrimental damage to the heart, blood vessels, eyes, kidneys and nerves. There are 2 types of diabetes, but we will not cover the distinction between the two and just contemplate if the patient has or does not have diabetes, as shown on the plot below.6

It seems clear that there is no relationship between having diabetes and the DEATH\_EVENT, since people having or not having diabetes have died and also there are more survivors than deaths. It is a similar plot like the anemia plot because they share the same binary values for the variables, and also it is similar to the other plots in the sense that they share the same colors for each possible outcome. *FIGURE 10*

To test the significance of this predictor we will perform a logistic regression test. This test shows that the p-value is extremely high, being close to p-value \= 1\. This is an evidence for the non-significance of this predictor in predicting the outcome for the response variable, not just at ɑ \= 0.05 but at no significance level practically. Furthermore, we confirm that the value 0 is right in the middle of our confidence interval at 95% which is another indication that there is a non-existent relationship between “diabetes” and “DEATH\_EVENT”. *FIGURE 11*

To check if our model is right, we compare it with the MLE parameters we have also computed, and we see that they are the same coefficients as the estimated ones. When visualizing the logistic regression curve we have plotted beneath, we see that the pattern is similar to the anemia plot, a rather flattened curve that down the line has more spikes, although prominently below the decision boundary line, which indicates that the impact is not clear since the predictor is not significant and the confidence interval is very large.FIGURE 12

**Ejection Fraction**  
The ejection fraction is the percentage of blood that leaves a ventricle when the heart beats and it measures the heart’s ability to pump oxygen-enriched blood to the body. A normal ejection fraction ranges between 52 and 72% for males and between 54 and 74% for females, although these percentages vary within age groups. The older we get, the less ejection fraction we produce. 7

The following boxplot shows us the percentage of ejection fraction and the death event outcome. At first glance we can appreciate that lower ejection fraction represents more death events, which is an unmistakable suggestion of a relationship between the variables. We performed a boxplot since the data was more visible this way. The light blue represents the death event while the dark blue represents the survival and we can see that the light blue box is larger than the other box, thus meaning there have been more departures than survivors.*FIGURE 13*

To reassure our initial statement, we created a model which was used to perform a logistic regression analysis. We see that the p-value is infimum which corroborates our hypothesis. To double-check we created the confidence interval for 95% confidence and the value 0 was not inside the confidence interval, which implies that the observed effect is statistically significant and there is enough evidence to suggest a real distinction in the population and a relationship between the two variables. The MLE parameters were exactly the same as the estimated coefficients in the logistic regression analysis so we can confirm that our model was built correctly. *FIGURE 14*

As we can examine from the logistic regression curve plot, the peaks and slopes are at an all-time high in this analysis, with astounding changes throughout the curve. The steeper the curve, the more influential the predictor is in predicting the outcome, this being that the ejection fraction is a significant predictor and causes a huge impact on the response variable.*FIGURE 15*

**High blood pressure**  
High blood pressure (also known as hypertension) is when the pressure in the blood vessels reaches a high enough level to cause harm. 8 Hypertension often develops over time and it can happen due to unhealthy lifestyle choices, such as not exercising regularly. Certain health conditions such as diabetes and obesity can also increase the risk of hypertension. 9

Since diabetes is a condition that can favor high blood pressure and knowing that diabetes is not a significant predictor for the response variable, we can assume that high blood pressures will not be a significant predictor either. When looking at the following barplot we see that there are much more survivors in both occasions (having or not having high blood pressure). It follows the same palette of colors as the diabetes plot and to confirm our initial guess we will carry out a logistic regression test.*FIGURE 16*

When searching for the p-value we can notice that it is not statistically significant for ɑ \= 0.05, thus confirming that our guess was well-founded. The other noticeable trait from this model is that the confidence interval for 95% confidence contains the value 0, to which we have seen in previous examples that it indicates non-significance and that there is a non-existent relationship between both variables. We also computed the MLE parameters to check if they differed from the coefficient estimates in the logistic regression model but it was not the case as we can witness.*FIGURE 17*

When plotting the logistic regression curve, we start with a flat line right at the decision boundary line located at 0.5 in the death event axis (just like all the other decision boundary lines). The spikes begin to increase but not drastically as we have seen on the previous plot. The peaks tend to the lower values of the death event axis, thus denying any chance for high blood pressure to become a significant predictor, not only but also approving our initial guess once more.*FIGURE 18*  
**Platelets**  
Platelets (also known as thrombocytes) are colorless cell fragments that, despite its tiny size, form clots and stop bleeding. When the level of platelets is low, it prevents blood cells from clotting and can lead to vast amounts of blood loss.10 If the platelet count is too high then blood clots can form in blood vessels, which can block blood flow through the body. The donation of platelets help cancer, trauma, transplant and burn patients to recover faster and hospitals are in need of donors. 11 12

This plot is pretty similar to the ejection fraction plot above, since both of them are boxplots. Although the death event box seems larger than the survival, we can confidently say that since they are on the same level, that platelets are not a significant predictor because on the same quantity of platelets there are more death events than survivors. If they were not on the same level, then we could guess that maybe it is a significant predictor.To test our hypothesis we will create a model and test it using a logistic regression test*.FIGURE 19*

As we can perceive from the p-value, it is not statistically significant for ɑ \= 0.05. To double-check, we compute the 95% confidence interval in order to search for the value 0 in the interval. What this information indicates is that there is no difference in the population, and any variation in the sample can be explained by random chance. Nonetheless, we computed the  
MLE parameters to see if the estimated coefficients matched and they did, as expected.*FIGURE 20*

The results from the logistic regression curve plot do not shock us since the peaks are situated where we expected, right under the decision boundary line. The highest death event value is situated at 0.5 which is the first one, and from there the curve decreases. We could interpret a negative correlation, since the plot shows us that having more platelets decreases the response variable, but we can discard this interpretation since the p-value is not statistically significant and the confidence   
interval has confirmed that this can be explained by random chance. Keeping all of this information in mind, we can conclude that there exists no relationship between the quantity of platelets and the response variable.*FIGURE 21*

**Serum creatinine**  
Creatinine is a waste product of the blood that comes from the muscles. Healthy kidneys filter out the creatinine of the blood through urine.13 The serum creatinine level is based on a blood test that measures the amount of creatinine in the blood, while also providing insight into how the kidneys are currently working. High creatinine levels that reach 5.0 in adults might indicate severe kidney impairment, which can lead to chronic kidney disease.14 The risk for cardiovascular disease is increased in all stages of the impairment of renal function, and serum creatinine is used as a marker of diabetes and coronary artery disease.15

Based on previous knowledge of serum creatinine we wanted to check if it was a significant predictor of death event, which taking into account the consequences of high creatinine levels we can assume that it will. By looking at the boxplot we created we can detect that there are more death events with higher levels of serum creatinine, but also that there are more death events in general. This is a notable marker for our hypothesis, and to confirm it we built a model and performed a logistic regression analysis. *FIGURE 22*

Our assumption was right, since the p-value is very much statistically significant for ɑ \= 0.05. What we did in order to check that the significance was not due to random chance was to compute the 95% confidence interval for 95% confidence and see if the value 0 lied between the interval, which it does not. The absence of this value serves as a critical indicator for assessing the statistical significance of the results, in this case reassuring the relationship between high levels of serum creatinine and death events. The MLE parameters were proposed to validate the veracity of the model we generated and as we can see, it concurs with the estimated coefficients in our model. *FIGURE 23*

The strong association between serum creatinine and the response variable makes the logistic regression curve plot have drastic steep changes, with the direction of the curve sloping upward and downward. This is suggestive of higher values being linked to an increased probability of the death event, thus confirming that the predictor “serum creatinine” is significant and has an effect on the response variable.*FIGURE 24*

**Serum sodium**  
The sodium blood test measures the concentration of sodium in the blood, but it can also be measured using a urine test. This test is performed by drawing blood from a vein, usually from the inside of the elbow.16 Hypernatremia is the condition caused by high serum sodium levels, and involves dehydration which can lead to muscle twitches and seizures. This can be caused by diarrhea, not drinking enough fluids or kidney dysfunction, among others. On the other hand, hyponatremia is the condition in which an individual has low levels of serum sodium, and symptoms may include nausea and vomiting, confusion or loss of energy. If not treated it can cause seizures, coma and even death.17 18

The following boxplot represents the possible relationship between levels of serum sodium and death events. It seems plausible to assume that the relationship does in fact exist, not only due to the death event box being larger than the survivor box but also the location, since it is situated on lower levels of serum sodium.*FIGURE 25*  
To clear up doubts, we conducted a logistic regression analysis to attest our assumption. 

As we can detect, the p-value is statistically significant for ɑ \= 0.05 and to double-check we will calculate the 95% confidence interval for 95% confidence and validate our initial hypothesis. The interval does not include the value 0, which if it did would signify that the predictor is not significant to the changes in the response variable. When comparing the estimated coefficients to the MLE parameters we can also corroborate that they are the same coefficients, which means that our model has been conducted accordingly. *FIGURE 26*

What the logistic regression curve plot displays is a series of steep slopes, which is an obvious sign of an ongoing relationship between the two variables. A trait of this plot is starting the curve at 1.0 value of the death event (which is uncommon for this type of graphs) but it can be explained since it has a negative correlation, which means that the lower the values of serum sodium, the greater the chance of the death event occurring.*FIGURE 27*

**Sex**  
Cardiovascular disease is the leading cause of death worldwide, yet some distinctions are key between males and females. Men generally develop CVD at younger ages than women, and have a higher coronary heart disease risk. In contrast, women are at a higher risk of stroke, occurring more often at older ages.19 Among other differences, men typically develop a plaque buildup in the large arteries that supply blood to the heart and women are more likely to develop this buildup in the heart’s smallest vessels, commonly known as the microvasculature. Heart disease in both sexes is partly related to the accumulation of cholesterol and overall the presence of coronary artery disease is lower in women.20

The barplot beside includes 2 columns, the left one being the count for women and the right one the count for men. As we observe the plot, we can clearly appreciate the difference between men and women, since there are more men than women in this dataset and also more death events in men than in women*FIGURE 28.* We can predict that it will be a significant predictor since more men than women have triggered the response variable and we will try to prove it statistically by performing a logistic regression test.

To our surprise, the p-value for the predictor variable was not statistically significant for ɑ \= 0.05, nowhere near close to being significant. This value brings us to the conclusion that the value 0 must be in the 95% confidence interval, so we will create it. With further inspection we see that inevitably the parameter 0 lies right in the middle of the confidence interval, which confirms that our hypothesis is not right and that the predictor sex is not significant for the changes in the response variable. Nevertheless, we evaluate the MLE parameters and approve the correctness of the model, since the estimated coefficients match.*FIGURE 29*

In addition, the logistic regression curve plot helps us visualize the non-significance of the predictor, since the steeps are tending to lower values of the death event. We can also conclude that a possible impact of the predictor on the response variable can be due to random chance, since we have seen and proven by multiple methods the lack of significance of the predictor.*FIGURE 30*  
**Smoking**  
Smoking is a major cause of cardiovascular disease, and causes approximately one of every four deaths from CVD. CVD is the single largest cause of death around the world, killing more than 800,000 people a year only in the United States.21 This activity is a major risk factor for heart disease since the chemicals inhaled when smoking cause damage to the heart and blood vessels, making you more likely to develop plaque buildup in the arteries. Cigarette smokers are twice to four times more likely to develop some type of CVD than non-smokers, and it doubles a person’s risk for stroke.22 23

The plot clearly illustrates that people that smoke survive far more than they die, so we can suppose that there will not be a relationship between the two variables. The non-smokers are situated on the left side of the plot, since value 0 indicates that they do not smoke, while the right side indicates that they do. Despite the previous knowledge, in this dataset it seems pretty clear that the predictor “smoking” will not be statistically significant *FIGURE 31*.   
To test this hypothesis we will assemble a logistic regression model.

As we imagined, the p-value is not statistically significant for ɑ \= 0.05. This also points out that the value 0 will lie between the CI which is not bold to predict since the predictor has no significance whatsoever on the response variable. We do in fact perceive that the value 0 falls within the range of both percentiles. Let’s not forget that we have to authenticate the reliability of the model, so we are going to figure out what the MLE parameters will be. Now we can finally confirm that the model is reliable, since the MLE parameters are the spittin image of the estimated coefficients in our logistic regression model.*FIGURE 32* 

Besides, the logistic regression curve plot is crucial to substantiate our hypothesis, considering that the curve lies beneath the decision boundary line, and the tendency to lower values of death events is noticeable. What makes this plot interesting is that it shows that smoking has more deaths than non-smoking, but this could be due to random chance or due to causes of death not related to heart diseases.*FIGURE 33*

**Final model**  
First of all, we created a model that included all of the predictors, and we were surprised to see that CPK had turned out to be statistically significant, and serum sodium was no longer statistically significant. 

We then plotted the effects of each variable on the response variable and observed that the significant predictors had a diagonal plot. The approach we took for the next model was simple, we only took into account the significant predictors and we found out that serum sodium was still not statistically significant. *FIGURE 34*

We also checked for multicollinearity which had a negative result in our data set since there is no  type of correlation between significant predictor variables While iterating through all of the predictors and taking out the one that had the highest p-value without losing information, we checked if there were changes on the other p-values, which there were since there were predictors somewhat correlated to each other.*FIGURE 35* 

The final model had the following parameters which computed this prediction table and as we have proven in the R code below, it is the exact same table, with a 77% chance of correctly predicting the outcome on the response variable.*FIGURE 36*

***4\. Conclusions***  
3 out of 11 possible predictors were significant (age, ejection fraction and serum creatinine), so those were the only ones needed to predict the probability of having a heart disease. The model built forecasts 77% of the cases. By adding more predictors to the data set we could possibly increase the chance of prognosis and by doing so the efficiency and accuracy of the model would rise.

***5\. Bibliography***

\[1\] How the Heart Works | Congenital Heart Defects | NCBDDD | CDC. (2018, 26 septiembre). Centers for Disease Control and Prevention. [https://www.cdc.gov/ncbddd/spanish/heartdefects/howtheheartworks.html](https://www.cdc.gov/ncbddd/spanish/heartdefects/howtheheartworks.html)

\[2\] UCI Machine Learning Repository. (s. f.). [https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records](https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records)

\[3\] Cardiovascular heart disease. (s. f.). British Heart Foundation. [https://www.bhf.org.uk/informationsupport/conditions/cardiovascular-heart-disease](https://www.bhf.org.uk/informationsupport/conditions/cardiovascular-heart-disease)

\[4\] What is anemia? | NHLBI, NIH. (2022, 24 marzo). NHLBI, NIH. [https://www.nhlbi.nih.gov/health/anemia](https://www.nhlbi.nih.gov/health/anemia)

\[5\] Creatine phosphokinase test. (s. f.). Mount Sinai Health System. [https://www.mountsinai.org/health-library/tests/creatine-phosphokinase-test](https://www.mountsinai.org/health-library/tests/creatine-phosphokinase-test)

\[6\] World Health Organization: WHO. (2019, 13 mayo). Diabetes. [https://www.who.int/health-topics/diabetes](https://www.who.int/health-topics/diabetes)

\[7\] Carroll, M., PhD. (2023, 25 junio). Everything you need to know about Ejection fraction. Healthline. [https://www.healthline.com/health/ejection-fraction](https://www.healthline.com/health/ejection-fraction)

\[8\] World Health Organization: WHO & World Health Organization: WHO. (2023, 16 marzo). Hypertension. [https://www.who.int/news-room/fact-sheets/detail/hypertension](https://www.who.int/news-room/fact-sheets/detail/hypertension)

\[9\] High blood pressure symptoms, causes, and problems | Cdc.gov. (2023, 29 agosto). Centers for Disease Control and Prevention. [https://www.cdc.gov/bloodpressure/about.htm](https://www.cdc.gov/bloodpressure/about.htm)

\[10\] What are platelets in blood. (s. f.). [https://www.redcrossblood.org/donate-blood/dlp/platelet-information.html](https://www.redcrossblood.org/donate-blood/dlp/platelet-information.html)

\[11\] What causes a low platelet count? (s. f.). [https://www.oneblood.org/media/blog/platelets/what-causes-a-low-platelet-count.stml](https://www.oneblood.org/media/blog/platelets/what-causes-a-low-platelet-count.stml)

\[12\] Thrombocythemia and thrombocytosis | NHLBI, NIH. (2022, 24 marzo). NHLBI, NIH. [https://www.nhlbi.nih.gov/health/thrombocythemia-thrombocytosis](https://www.nhlbi.nih.gov/health/thrombocythemia-thrombocytosis)

\[13\] American Kidney Fund. (2023, 10 noviembre). Serum creatinine test. [https://www.kidneyfund.org/all-about-kidneys/tests/serum-creatinine-test](https://www.kidneyfund.org/all-about-kidneys/tests/serum-creatinine-test)

\[14\] High creatinine levels can indicate chronic kidney disease. (s. f.). UCLA Health. [https://www.uclahealth.org/news/high-creatinine-levels-can-indicate-chronic-kidney-disease](https://www.uclahealth.org/news/high-creatinine-levels-can-indicate-chronic-kidney-disease)

\[15\] Bagheri, B., Radmard, N., Faghani-Makrani, A., & Rasouli, M. (2019). Serum creatinine and occurrence and severity of coronary artery disease. Medicinski arhiv, 73(3), 154\. [https://doi.org/10.5455/medarh.2019.73.154-156](https://doi.org/10.5455/medarh.2019.73.154-156)

\[16\] Sodium blood test. (s. f.). Mount Sinai Health System. [https://www.mountsinai.org/health-library/tests/sodium-blood-test](https://www.mountsinai.org/health-library/tests/sodium-blood-test)

\[17\] Lewis, J. L., III. (2023, 12 noviembre). Hypernatremia (High level of sodium in the blood). MSD Manual Consumer Version. [https://www.msdmanuals.com/en-gb/home/hormonal-and-metabolic-disorders/electrolyte-balance/hypernatremia-high-level-of-sodium-in-the-blood](https://www.msdmanuals.com/en-gb/home/hormonal-and-metabolic-disorders/electrolyte-balance/hypernatremia-high-level-of-sodium-in-the-blood)

\[18\] Low blood sodium in older adults: a concern? (2023, 16 mayo). Mayo Clinic. [https://www.mayoclinic.org/diseases-conditions/hyponatremia/expert-answers/low-blood-sodium/faq-20058465](https://www.mayoclinic.org/diseases-conditions/hyponatremia/expert-answers/low-blood-sodium/faq-20058465)

\[19\] Bots, S. H., Peters, S. A., & Woodward, M. (2017). Sex Differences in Coronary heart Disease and Stroke Mortality: A Global Assessment of the Effect of ageing between 1980 and 2010\. BMJ Global Health, 2(2), e000298. [https://doi.org/10.1136/bmjgh-2017-000298](https://doi.org/10.1136/bmjgh-2017-000298)  
   
\[20\] Bwhgive. (2023, 5 octubre). 1908AGEMNL – AG Newsletter – 7 Differences between Men and women. Brigham and Women’s Hospital Giving. [https://give.brighamandwomens.org/7-differences-between-men-and-women/](https://give.brighamandwomens.org/7-differences-between-men-and-women/)

\[21\] SMOKING AND CARDIOVASCULAR DISEASE. (s/f). Cdc.gov, [https://www.cdc.gov/tobacco/sgr/50th-anniversary/pdfs/fs\_smoking\_cvd\_508.pdf](https://www.cdc.gov/tobacco/sgr/50th-anniversary/pdfs/fs_smoking_cvd_508.pdf)

\[22\] How smoking affects the heart and blood vessels | NHLBI, NIH. (2022, 24 marzo). NHLBI, NIH. [https://www.nhlbi.nih.gov/health/heart/smoking](https://www.nhlbi.nih.gov/health/heart/smoking)

\[23\] Smoking and cardiovascular disease. (2020, 20 julio). Johns Hopkins Medicine. [https://www.hopkinsmedicine.org/health/conditions-and-diseases/smoking-and-cardiovascular-disease](https://www.hopkinsmedicine.org/health/conditions-and-diseases/smoking-and-cardiovascular-disease)

***6\. Appendix***   
\# Load necessary libraries  
library(ggplot2)  
library(car)  
library(corrplot)  
library(lme4)  
library(broom)  
library(effects)

\# Read the data  
heart\_data \<- read.csv("heart\_failure\_clinical\_records\_dataset.csv")  
sapply(heart\_data, class)

table(heart\_data$DEATH\_EVENT)

round(prop.table(table(heart\_data$DEATH\_EVENT))\*100, digits \= 2\)

\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Death Event \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(DEATH\_EVENT), fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar() \+  
  xlab("Heart Disease") \+  
  ylab("Count") \+  
  ggtitle("Death events") \+  
  scale\_fill\_discrete(name \= "Heart Disease", labels \= c("Survive", "Death"))

\#\#\#\#\#\#\#\#\#\#  
\#\#\# Age \#\#\#  
\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= age, fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar() \+  
  xlab("Age") \+  
  ylab("Count") \+  
  ggtitle("Heart Disease vs Age") \+  
  scale\_fill\_discrete(name \= "Heart Disease", labels \= c("Survive", "Death"))

\# Age model

age \<- "age"

formula\_age \<- as.formula(paste("DEATH\_EVENT \~", age))

age\_model \<- glm(formula\_age, data \= heart\_data, family \= "binomial")

\# Check significance  
age\_summary \<- summary(age\_model)  
age\_summary  
\# Extract p-value  
age\_p\_value \<- age\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
age\_p\_value

\# Double-check if age is a significant predictor by computing CI  
age\_coefficient \<- coef(age\_model)  
age\_coefficient  
\# Get confidence intervals for coefficients  
age\_conf\_intervals \<- confint(age\_model)  
age\_conf\_intervals

\# Compute MLE parameters  
likelihood\_age \<- function(parameters, data) {  
  log\_odds\_age \<- parameters\[1\] \+ parameters\[2\] \* data$age  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_age))  
  log\_likelihood\_age \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                          	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_age)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_age, data \= heart\_data)

mle\_age\_parameters \<- result$par  
cat("MLE Parameters:", mle\_age\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
age\_values \<- seq(min(heart\_data$age), max(heart\_data$age), length.out \= 50\)  
log\_odds \<- age\_coefficient \* age\_values    
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$age, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Age", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Age")  
lines(age\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Anemia  \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(anaemia), fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar() \+  
  xlab("Anemia levels") \+  
  ylab("Count") \+  
  ggtitle("Levels of Anemia and Heart Disease") \+  
  scale\_fill\_discrete(name \= "Heart Disease", labels \= c("Survive", "Death"))

\# Anemia model  
anemia \<- "anaemia"

formula\_anemia \<- as.formula(paste("DEATH\_EVENT \~", anemia))

anemia\_model \<- glm(formula\_anemia, data \= heart\_data, family \= "binomial")

\# Check significance  
anemia\_summary \<- summary(anemia\_model)  
anemia\_summary

\# Extract p-value  
anemia\_p\_value \<- anemia\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
anemia\_p\_value

\# Double-check if anemia is a significant predictor by computing CI  
anemia\_coefficient \<- coef(anemia\_model)  
anemia\_coefficient  
\# Get confidence intervals for coefficients  
anemia\_conf\_intervals \<- confint(anemia\_model)  
anemia\_conf\_intervals

\# Compute MLE parameters  
likelihood\_anemia \<- function(parameters, data) {  
  log\_odds\_anemia \<- parameters\[1\] \+ parameters\[2\] \* data$anaemia  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_anemia))  
  log\_likelihood\_anemia \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                             	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_anemia)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_anemia, data \= heart\_data)

mle\_anemia\_parameters \<- result$par  
cat("MLE Parameters:", mle\_anemia\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
anemia\_values \<- seq(min(heart\_data$anaemia), max(heart\_data$anaemia), length.out \= 50\)  
log\_odds \<- anemia\_coefficient \* anemia\_values

probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$anaemia, heart\_data$DEATH\_EVENT, pch \= 16,  
 	col \= "blue", xlab \= "Anemia", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Anemia")  
lines(anemia\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))  
   
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Creatinine Phosphokinase \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \=creatinine\_phosphokinase, fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_histogram(position \= "dodge", bins \= 30, color \= "black", alpha \= 0.7) \+  
  xlab("Creatinine Phosphokinase") \+  
  ylab("Count") \+  
  ggtitle("Creatinine Phosphokinase vs. Death Event") \+  
  scale\_fill\_discrete(name \= "Death Event", labels \= c("Survive", "Death"))  
 

\# Creatinine Phosphokinase model  
creatinine\_phosphokinase \<- "creatinine\_phosphokinase"

formula\_creatinine \<- as.formula(paste("DEATH\_EVENT \~", creatinine\_phosphokinase))

creatinine\_model \<- glm(formula\_creatinine, data \= heart\_data, family \= "binomial")

\# Check significance  
creatinine\_summary \<- summary(creatinine\_model)  
creatinine\_summary

\# Extract p-value  
creatinine\_p\_value \<- creatinine\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
creatinine\_p\_value

\# Double-check if creatinine phosphokinase is a significant predictor by computing CI  
creatinine\_coefficient \<- coef(creatinine\_model)  
creatinine\_coefficient  
\# Get confidence intervals for coefficients  
creatinine\_conf\_intervals \<- confint(creatinine\_model)  
creatinine\_conf\_intervals

\# Compute MLE parameters  
likelihood\_cp \<- function(parameters, data) {  
  log\_odds\_cp \<- parameters\[1\] \+ parameters\[2\] \* data$creatinine\_phosphokinase  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_cp))  
  log\_likelihood\_cp \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                         	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_cp)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_cp, data \= heart\_data)

mle\_cp\_parameters \<- result$par  
cat("MLE Parameters:", mle\_cp\_parameters, "\\n")

   
\# Plot to visualize the significance of the predictor  
creatinine\_values \<- seq(min(heart\_data$creatinine), max(heart\_data$creatinine), length.out \= 50\)  
log\_odds \<- creatinine\_coefficient \* creatinine\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$creatinine, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "CPK", ylab \= "Death Event", main \= "Logistic Regression Curve for CPK")  
lines(creatinine\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))  
 

\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Diabetes \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(diabetes), fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar(position \= "dodge", color \= "black", alpha \= 0.7) \+  
  xlab("Diabetes") \+  
  ylab("Count") \+  
  ggtitle("Diabetes vs. Death Event") \+  
  scale\_fill\_discrete(name \= "Death Event", labels \= c("Survive", "Death"))  
 

   
diabetes \<- "diabetes"

formula\_diabetes \<- as.formula(paste("DEATH\_EVENT \~", diabetes))

\# Diabetes model  
diabetes\_model \<- glm(formula\_diabetes, data \= heart\_data, family \= "binomial")

\# Check significance  
diabetes\_summary \<- summary(diabetes\_model)  
diabetes\_summary

\# Extract p-value  
diabetes\_p\_value \<- diabetes\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
diabetes\_p\_value  
   
\# Double-check if diabetes is a significant predictor by computing CI  
diabetes\_coefficient \<- coef(diabetes\_model)  
diabetes\_coefficient  
\# Get confidence intervals for coefficients  
diabetes\_conf\_intervals \<- confint(diabetes\_model)  
diabetes\_conf\_intervals

\# Compute MLE parameters  
likelihood\_diabetes \<- function(parameters, data) {  
  log\_odds\_diabetes \<- parameters\[1\] \+ parameters\[2\] \* data$diabetes  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_diabetes))  
  log\_likelihood\_diabetes \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                               	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_diabetes)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_diabetes, data \= heart\_data)

mle\_diabetes\_parameters \<- result$par  
cat("MLE Parameters:", mle\_diabetes\_parameters, "\\n")  
   
\# Plot to visualize the significance of the predictor  
diabetes\_values \<- seq(min(heart\_data$diabetes), max(heart\_data$diabetes), length.out \= 50\)  
log\_odds \<- diabetes\_coefficient \* diabetes\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$diabetes, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Diabetes", ylab \= "Death Event", main \= "Logistic Regression Curve for Diabetes")  
lines(diabetes\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Ejection fraction \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(DEATH\_EVENT), y \= ejection\_fraction, fill \= DEATH\_EVENT)) \+  
  geom\_boxplot() \+  
  xlab("Death Event") \+  
  ylab("Ejection Fraction") \+  
  ggtitle("Ejection Fraction vs. Death Event")  
   
\# Ejection fraction model  
ejection\_fraction \<- "ejection\_fraction"

formula\_ejection\_fraction \<- as.formula(paste("DEATH\_EVENT \~", ejection\_fraction))

ejection\_fraction\_model \<- glm(formula\_ejection\_fraction, data \= heart\_data, family \= "binomial")

\# Check significance  
ejection\_fraction\_summary \<- summary(ejection\_fraction\_model)  
ejection\_fraction\_summary  
\# Extract p-value  
ejection\_fraction\_p\_value \<- ejection\_fraction\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
ejection\_fraction\_p\_value

\# Double-check if ejection fraction is a significant predictor by computing CI  
ejection\_fraction\_coefficient \<- coef(ejection\_fraction\_model)  
ejection\_fraction\_coefficient  
\# Get confidence intervals for coefficients  
ejection\_fraction\_conf\_intervals \<- confint(ejection\_fraction\_model)  
ejection\_fraction\_conf\_intervals

\# Compute MLE parameters  
likelihood\_ej \<- function(parameters, data) {  
  log\_odds\_ej \<- parameters\[1\] \+ parameters\[2\] \* data$ejection\_fraction  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_ej))  
  log\_likelihood\_ej \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                         	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_ej)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_ej, data \= heart\_data)

mle\_ej\_parameters \<- result$par  
cat("MLE Parameters:", mle\_ej\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
ejection\_fraction\_values \<- seq(min(heart\_data$ejection\_fraction), max(heart\_data$ejection\_fraction), length.out \= 50\)  
log\_odds \<- ejection\_fraction\_coefficient \* ejection\_fraction\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$ejection\_fraction, heart\_data$DEATH\_EVENT, pch \= 16,  
 	col \= "blue", xlab \= "ejection\_fraction", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Ejection fraction")  
lines(ejection\_fraction\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# High blood pressure \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(high\_blood\_pressure), fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar(position \= "dodge", color \= "black", alpha \= 0.7) \+  
  xlab("High Blood Pressure") \+  
  ylab("Count") \+  
  ggtitle("High Blood Pressure vs. Death Event") \+  
  scale\_fill\_discrete(name \= "Death Event", labels \= c("Survive", "Death"))  
 

\# High blood pressure model    
hbp \<- "high\_blood\_pressure"

formula\_hbp \<- as.formula(paste("DEATH\_EVENT \~", hbp))

hbp\_model \<- glm(formula\_hbp, data \= heart\_data, family \= "binomial")

\# Check significance  
hbp\_summary \<- summary(hbp\_model)  
hbp\_summary  
\# Extract p-value  
hbp\_p\_value \<- hbp\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
hbp\_p\_value

\# Double-check if high blood pressure is a significant predictor by computing CI  
hbp\_coefficient \<- coef(hbp\_model)  
hbp\_coefficient  
\# Get confidence intervals for coefficients  
hbp\_conf\_intervals \<- confint(hbp\_model)  
hbp\_conf\_intervals

\# Compute MLE parameters  
likelihood\_hbp \<- function(parameters, data) {  
  log\_odds\_hbp \<- parameters\[1\] \+ parameters\[2\] \* data$high\_blood\_pressure  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_hbp))  
  log\_likelihood\_hbp \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                          	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_hbp)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_hbp, data \= heart\_data)

mle\_hbp\_parameters \<- result$par  
cat("MLE Parameters:", mle\_hbp\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
hbp\_values \<- seq(min(heart\_data$high\_blood\_pressure), max(heart\_data$high\_blood\_pressure), length.out \= 50\)  
log\_odds \<- hbp\_coefficient \* hbp\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$high\_blood\_pressure, heart\_data$DEATH\_EVENT, pch \= 16,  
 	col \= "blue", xlab \= "hbp", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for High Blood Pressure")  
lines(hbp\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Platelets \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(DEATH\_EVENT), y \= platelets, fill \= DEATH\_EVENT)) \+  
  geom\_boxplot() \+  
  xlab("Death Event") \+  
  ylab("Platelets") \+  
  ggtitle("Platelets vs. Death Event")  
 

\# Platelets model  
platelets \<- "platelets"

formula\_platelets \<- as.formula(paste("DEATH\_EVENT \~", platelets))

platelets\_model \<- glm(formula\_platelets, data \= heart\_data, family \= "binomial")

\# Check significance  
platelets\_summary \<- summary(platelets\_model)  
platelets\_summary  
\# Extract p-value  
platelets\_p\_value \<- platelets\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
platelets\_p\_value

\# Double-check if platelets is a significant predictor by computing CI  
platelets\_coefficient \<- coef(platelets\_model)  
platelets\_coefficient  
\# Get confidence intervals for coefficients  
platelets\_conf\_intervals \<- confint(platelets\_model)  
platelets\_conf\_intervals

\# Compute MLE parameters  
likelihood\_platelets \<- function(parameters, data) {  
  log\_odds\_platelets \<- parameters\[1\] \+ parameters\[2\] \* data$platelets  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_platelets))  
  log\_likelihood\_platelets \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                                	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_platelets)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_platelets, data \= heart\_data)

mle\_platelets\_parameters \<- result$par  
cat("MLE Parameters:", mle\_platelets\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
platelets\_values \<- seq(min(heart\_data$platelets), max(heart\_data$platelets), length.out \= 50\)  
log\_odds \<- platelets\_coefficient \* platelets\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$platelets, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Platelets", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Platelets")  
lines(platelets\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))  
   
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Serum creatinine \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(DEATH\_EVENT), y \= serum\_creatinine, fill \= DEATH\_EVENT)) \+  
  geom\_boxplot() \+  
  xlab("Death Event") \+  
  ylab("Serum Creatinine") \+  
  ggtitle("Serum Creatinine vs. Death Event")  
 

\# Serum creatinine model  
serum\_creatinine \<- "serum\_creatinine"

formula\_serum\_creatinine \<- as.formula(paste("DEATH\_EVENT \~", serum\_creatinine))

serum\_creatinine\_model \<- glm(formula\_serum\_creatinine, data \= heart\_data, family \= "binomial")

\# Check significance  
serum\_creatinine\_summary \<- summary(serum\_creatinine\_model)  
serum\_creatinine\_summary  
\# Extract p-value  
serum\_creatinine\_p\_value \<- serum\_creatinine\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
serum\_creatinine\_p\_value  
   
\# Double-check if serum creatinine is a significant predictor by computing CI  
serum\_creatinine\_coefficient \<- coef(serum\_creatinine\_model)  
serum\_creatinine\_coefficient  
\# Get confidence intervals for coefficients  
serum\_creatinine\_conf\_intervals \<- confint(serum\_creatinine\_model)  
serum\_creatinine\_conf\_intervals

\# Compute MLE parameters  
likelihood\_sc \<- function(parameters, data) {  
  log\_odds\_sc \<- parameters\[1\] \+ parameters\[2\] \* data$serum\_creatinine  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_sc))  
  log\_likelihood\_sc \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                         	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_sc)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_sc, data \= heart\_data)

mle\_sc\_parameters \<- result$par  
cat("MLE Parameters:", mle\_sc\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
serum\_creatinine\_values \<- seq(min(heart\_data$serum\_creatinine), max(heart\_data$serum\_creatinine), length.out \= 50\)  
log\_odds \<- serum\_creatinine\_coefficient \* serum\_creatinine\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$serum\_creatinine, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Serum Creatinine", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Serum Creatinine")  
lines(serum\_creatinine\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Serum sodium \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= as.factor(DEATH\_EVENT), y \= serum\_sodium, fill \= DEATH\_EVENT)) \+  
  geom\_boxplot() \+  
  xlab("Death Event") \+  
  ylab("Serum sodium") \+  
  ggtitle("Serum Sodium vs. Death Event")  
 

\# Serum sodium model  
serum\_sodium \<- "serum\_sodium"

formula\_serum\_sodium \<- as.formula(paste("DEATH\_EVENT \~", serum\_sodium))

serum\_sodium\_model \<- glm(formula\_serum\_sodium, data \= heart\_data, family \= "binomial")

\# Check significance  
serum\_sodium\_summary \<- summary(serum\_sodium\_model)  
serum\_sodium\_summary  
\# Extract p-value  
serum\_sodium\_p\_value \<- serum\_sodium\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
serum\_sodium\_p\_value

\# Double-check if serum sodium is a significant predictor by computing CI  
serum\_sodium\_coefficient \<- coef(serum\_sodium\_model)  
serum\_sodium\_coefficient  
\# Get confidence intervals for coefficients  
serum\_sodium\_conf\_intervals \<- confint(serum\_sodium\_model)  
serum\_sodium\_conf\_intervals

\# Compute MLE parameters  
likelihood\_ss \<- function(parameters, data) {  
  log\_odds\_ss \<- parameters\[1\] \+ parameters\[2\] \* data$serum\_sodium  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_ss))  
  log\_likelihood\_ss \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                         	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_ss)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_ss, data \= heart\_data)

mle\_ss\_parameters \<- result$par  
cat("MLE Parameters:", mle\_ss\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
serum\_sodium\_values \<- seq(min(heart\_data$serum\_sodium), max(heart\_data$serum\_sodium), length.out \= 50\)  
log\_odds \<- serum\_sodium\_coefficient \* serum\_sodium\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$serum\_sodium, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Serum Sodium", ylab \= "Death Event",  
 	main \= "Logistic Regression Curve for Serum Sodium")  
lines(serum\_sodium\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))

\#\#\#\#\#\#\#\#\#\#  
\#\#\# Sex \#\#\#  
\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= sex, fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar() \+  
  xlab("Sex") \+  
  ylab("Count") \+  
  ggtitle("Heart Disease Female vs Male") \+  
  scale\_fill\_discrete(name \= "Heart Disease", labels \= c("Survive", "Death"))  
 

\# Sex model  
sex \<- "sex"

formula\_sex \<- as.formula(paste("DEATH\_EVENT \~", sex))

sex\_model \<- glm(formula\_sex, data \= heart\_data, family \= "binomial")

\# Check significance  
sex\_summary \<- summary(sex\_model)  
sex\_summary  
\# Extract p-value  
sex\_p\_value \<- sex\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
sex\_p\_value

\# Double-check if sex is a significant predictor by computing CI  
sex\_coefficient \<- coef(sex\_model)  
sex\_coefficient  
\# Get confidence intervals for coefficients  
sex\_conf\_intervals \<- confint(sex\_model)  
sex\_conf\_intervals

\# Compute MLE parameters  
likelihood\_sex \<- function(parameters, data) {  
  log\_odds\_sex \<- parameters\[1\] \+ parameters\[2\] \* data$sex  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_sex))  
  log\_likelihood\_sex \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                          	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_sex)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_sex, data \= heart\_data)

mle\_sex\_parameters \<- result$par  
cat("MLE Parameters:", mle\_sex\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
sex\_values \<- seq(min(heart\_data$sex), max(heart\_data$sex), length.out \= 50\)  
log\_odds \<- sex\_coefficient \* sex\_values     
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$sex, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Sex", ylab \= "Death Event", main \= "Logistic Regression Curve for Sex")  
lines(sex\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))  
   
\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Smoking \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#  
ggplot(heart\_data, aes(x \= smoking, fill \= as.factor(DEATH\_EVENT))) \+  
  geom\_bar(position \= "dodge", color \= "black", alpha \= 0.7) \+  
  xlab("Smoking") \+  
  ylab("Count") \+  
  ggtitle("Smoking vs. Death Event") \+  
  scale\_fill\_discrete(name \= "Death Event", labels \= c("Survive", "Death"))  
 

\# Smoking model  
smoking \<- "smoking"

formula\_smoking \<- as.formula(paste("DEATH\_EVENT \~", smoking))

smoking\_model \<- glm(formula\_smoking, data \= heart\_data, family \= "binomial")

\# Check significance  
smoking\_summary \<- summary(smoking\_model)  
smoking\_summary  
\# Extract p-value  
smoking\_p\_value \<- smoking\_summary$coefficients\[, "Pr(\>|z|)"\]\[2\]  
smoking\_p\_value

\# Double-check if smoking is a significant predictor by computing CI  
smoking\_coefficient \<- coef(smoking\_model)  
smoking\_coefficient  
\# Get confidence intervals for coefficients  
smoking\_conf\_intervals \<- confint(smoking\_model)  
smoking\_conf\_intervals

\# Compute MLE parameters  
likelihood\_smoking \<- function(parameters, data) {  
  log\_odds\_smoking \<- parameters\[1\] \+ parameters\[2\] \* data$smoking  
  probabilities \<- 1 / (1 \+ exp(-log\_odds\_smoking))  
  log\_likelihood\_smoking \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                              	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood\_smoking)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- c(0, 0\)

result \<- optim(par \= initial\_parameters, fn \= likelihood\_smoking, data \= heart\_data)

mle\_smoking\_parameters \<- result$par  
cat("MLE Parameters:", mle\_smoking\_parameters, "\\n")

\# Plot to visualize the significance of the predictor  
smoking\_values \<- seq(min(heart\_data$smoking), max(heart\_data$smoking), length.out \= 50\)  
log\_odds \<- smoking\_coefficient \* smoking\_values  
probability \<- 1 / (1 \+ exp(-log\_odds))

\# Plotting  
plot(heart\_data$smoking, heart\_data$DEATH\_EVENT, pch \= 16, col \= "blue",  
 	xlab \= "Smoking", ylab \= "Death Event", main \= "Logistic Regression Curve for Smoking")  
lines(smoking\_values, probability, col \= "red", lwd \= 2\)

\# Adding a horizontal line at y \= 0.5 (decision boundary)  
abline(h \= 0.5, col \= "green", lty \= 2\)

\# Adding legend  
legend("topright", legend \= c("Data", "Logistic Curve", "Decision Boundary"),  
   	col \= c("blue", "red", "green"), lty \= c(NA, 1, 2), pch \= c(16, NA, NA))  
   
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Classification of predictors \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
alpha \<- 0.05

predictors \<- c(age, anemia, creatinine\_phosphokinase, diabetes,  
            	ejection\_fraction, hbp, platelets, serum\_creatinine,  
            	serum\_sodium, sex, smoking)

p\_values \<- c(age\_p\_value, anemia\_p\_value, creatinine\_p\_value, diabetes\_p\_value,  
          	ejection\_fraction\_p\_value, hbp\_p\_value, platelets\_p\_value,  
          	serum\_creatinine\_p\_value, serum\_sodium\_p\_value, sex\_p\_value,  
          	smoking\_p\_value)

if (any(p\_values \< alpha)) {  
  significant\_predictors \<- predictors\[p\_values \< alpha\]  
   
  cat("Significant predictors:", paste(significant\_predictors, collapse \= ", "), "\\n")  
  cat("Corresponding p-values:", paste(p\_values\[p\_values \< alpha\], collapse \= ", "), "\\n\\n")

}

if (any(p\_values \> alpha)){  
	non\_significant\_predictors \<- predictors\[p\_values \> alpha\]  
      
	cat("Non-significant predictors:", paste(non\_significant\_predictors, collapse \= ", "), "\\n")  
	cat("Corresponding p-values:", paste(p\_values\[p\_values \> alpha\], collapse \= ", "), "\\n")  
}  
 

\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# All model \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
all\_model\_formula \<- as.formula(paste("DEATH\_EVENT \~", paste(predictors, collapse \= " \+ ")))

all\_model \<- glm(all\_model\_formula, data \= heart\_data, family \= "binomial")

\# Check significance  
all\_summary \<- summary(all\_model)  
all\_summary  
   
\# Check if there are significant predictors by computing CI  
coefficients \<- coef(all\_model)

\# Get confidence intervals for coefficients  
conf\_intervals \<- confint(all\_model)

\# Display the results  
results \<- data.frame(coefficients, conf\_intervals)  
print(results)

\# Compute MLE parameters  
likelihood \<- function(parameters, data) {  
  log\_odds \<- parameters\[1\] \+ sum(parameters\[2:length(parameters)\] \* data\[, 2:ncol(data)\])  
  probabilities \<- 1 / (1 \+ exp(-log\_odds))  
  log\_likelihood \<- sum(data$DEATH\_EVENT \* log(probabilities) \+  
                      	(1 \- data$DEATH\_EVENT) \* log(1 \- probabilities))  
  return(-log\_likelihood)  \# We want to maximize, so we minimize the negative log likelihood  
}

initial\_parameters \<- rep(0, ncol(heart\_data)-2)

result \<- optim(par \= initial\_parameters, fn \= likelihood, data \= heart\_data)  
mle\_parameters \<- result$par  
cat("MLE Parameters:", mle\_parameters, "\\n")

   
\# Create effects plot  
effect\_all \<- allEffects(all\_model)  
plot(effect\_all, col \= "red", lines \= TRUE, rug \= FALSE)

\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#  
\#\#\# Significant model \#\#\#  
\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#\#

significant\_model\_formula \<- as.formula(paste("DEATH\_EVENT \~", paste(significant\_predictors, collapse \= " \+ ")))

significant\_model \<- glm(significant\_model\_formula, data \= heart\_data, family \= "binomial")

\# Check significance  
significant\_summary \<- summary(significant\_model)  
significant\_summary  
   
\# Double-check if the significant predictors are significant by computing CI  
significant\_coefficient \<- coef(significant\_model)  
significant\_coefficient  
\# Get confidence intervals for coefficients  
significant\_conf\_intervals \<- confint(significant\_model)  
significant\_conf\_intervals  
 

\# Create effects plot  
effect\_sign \<- allEffects(significant\_model)  
plot(effect\_sign, col \= "red", lines \= TRUE, rug \= FALSE)

\# Correlation matrix between predictors to check for multicollinearity  
corr\_matrix \<- cor(heart\_data\[predictors\])  
corr\_matrix  
corrplot(corr\_matrix, method \= "color")

\# Alternative way to check for multicollinearity  
vif\_values \<- car::vif(all\_model)  
vif\_values

\# NO values between 5-10, no collinearity  
 

\# Create a model with all predictors except smoking since it has the highest p-value  
not\_smoking\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ anaemia \+ creatinine\_phosphokinase  
                     	\+ diabetes \+ ejection\_fraction \+ high\_blood\_pressure \+ platelets \+ serum\_creatinine  
                     	\+ serum\_sodium \+ sex, data \= heart\_data, family \= "binomial")

\# Check significance  
not\_smoking\_summary \<- summary(not\_smoking\_model)  
not\_smoking\_summary

\# Little increase in deviance, anova test not to lose info  
not\_smoking\_anova \<- anova(all\_model, not\_smoking\_model, test \= "Chisq")  
not\_smoking\_anova  
   
   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except platelets since it has the highest p-value  
not\_platelets\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ anaemia \+ creatinine\_phosphokinase  
                     	\+ diabetes \+ ejection\_fraction \+ high\_blood\_pressure \+ serum\_creatinine  
                     	\+ serum\_sodium \+ sex, data \= heart\_data, family \= "binomial")

\# Check significance  
not\_platelets\_summary \<- summary(not\_platelets\_model)  
not\_platelets\_summary

\# Little increase in deviance, anova test not to lose info  
not\_platelets\_anova \<- anova(all\_model, not\_platelets\_model, test \= "Chisq")  
not\_platelets\_anova  
   
   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except diabetes since it has the highest p-value  
not\_diabetes\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ anaemia \+ creatinine\_phosphokinase  
                     	\+ ejection\_fraction \+ high\_blood\_pressure \+ serum\_creatinine  
                     	\+ serum\_sodium \+ sex, data \= heart\_data, family \= "binomial")

\# Check significance  
not\_diabetes\_summary \<- summary(not\_diabetes\_model)  
not\_diabetes\_summary

\# Little increase in deviance, anova test not to lose info  
not\_diabetes\_anova \<- anova(all\_model, not\_diabetes\_model, test \= "Chisq")  
not\_diabetes\_anova  
 

   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except sex since it has the highest p-value  
not\_sex\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ anaemia \+ creatinine\_phosphokinase  
                     	\+ ejection\_fraction \+ high\_blood\_pressure \+ serum\_creatinine  
                     	\+ serum\_sodium, data \= heart\_data, family \= "binomial")

\# Check significance  
not\_sex\_summary \<- summary(not\_sex\_model)  
not\_sex\_summary

\# Little increase in deviance, anova test not to lose info  
not\_sex\_anova \<- anova(all\_model, not\_sex\_model, test \= "Chisq")  
not\_sex\_anova  
 

   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except anemia since it has the highest p-value  
not\_anemia\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ creatinine\_phosphokinase  
                     	\+ ejection\_fraction \+ high\_blood\_pressure \+ serum\_creatinine  
                     	\+ serum\_sodium, data \= heart\_data, family \= "binomial")

\# Check significance  
not\_anemia\_summary \<- summary(not\_anemia\_model)  
not\_anemia\_summary

\# Little increase in deviance, anova test not to lose info  
not\_anemia\_anova \<- anova(all\_model, not\_anemia\_model, test \= "Chisq")  
not\_anemia\_anova  
 

   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except serum\_sodium since it has the highest p-value  
not\_serum\_sodium\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ creatinine\_phosphokinase  
                     	\+ ejection\_fraction \+ high\_blood\_pressure \+ serum\_creatinine,  
                     	data \= heart\_data, family \= "binomial")

\# Check significance  
not\_serum\_sodium\_summary \<- summary(not\_serum\_sodium\_model)  
not\_serum\_sodium\_summary

\# Little increase in deviance, anova test not to lose info  
not\_serum\_sodium\_anova \<- anova(all\_model, not\_serum\_sodium\_model, test \= "Chisq")  
not\_serum\_sodium\_anova  
 

   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except creatinine since it has the highest p-value  
not\_creatinine\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ ejection\_fraction  
                    	\+ high\_blood\_pressure \+ serum\_creatinine,  
                    	data \= heart\_data, family \= "binomial")  
\# Check significance  
not\_creatinine\_summary \<- summary(not\_creatinine\_model)  
not\_creatinine\_summary

\# Little increase in deviance, anova test not to lose info  
not\_creatinine\_anova \<- anova(all\_model, not\_creatinine\_model, test \= "Chisq")  
not\_creatinine\_anova  
 

   
\# We have not lost info, p-value non-significant  
\# Create a model with all predictors except hbp since it has the highest p-value  
not\_hbp\_model \<- glm(formula \= DEATH\_EVENT \~ age \+ ejection\_fraction \+ serum\_creatinine,  
                    	data \= heart\_data, family \= "binomial")  
\# Check significance  
not\_hbp\_summary \<- summary(not\_hbp\_model)  
not\_hbp\_summary

\# Little increase in deviance, anova test not to lose info  
not\_hbp\_anova \<- anova(all\_model, not\_hbp\_model, test \= "Chisq")  
not\_hbp\_anova

\# Compute probabilities for the final model  
final\_model \<- not\_hbp\_model  
summary(final\_model)

heart\_data$prob\_pred \<- predict(final\_model, newdata \= heart\_data, type \= "response")

heart\_data$prediction \<- cut(heart\_data$prob\_pred, breaks \= c(0, 0.5, 1), labels \= c(0, 1))  
attach(heart\_data)  
table(heart\_data$DEATH\_EVENT, heart\_data$prediction)

\# Compare probabilities with the all model  
heart\_data$prob\_pred \<- predict(all\_model, newdata \= heart\_data, type \= "response")

heart\_data$prediction \<- cut(heart\_data$prob\_pred, breaks \= c(0, 0.5, 1), labels \= c(0, 1))  
attach(heart\_data)  
table(heart\_data$DEATH\_EVENT, heart\_data$prediction)

\# Exactly the same numbers, the final model is reliable with 77% accuracy  

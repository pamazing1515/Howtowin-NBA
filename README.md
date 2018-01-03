# Howtowin-NBA
A project applying linear regression to 2015-2016 NBA data to model greatest factors that influence winning in the NBA

Background and Description of the Problem

Statistics used in sports have become more prominent not only for the fans who bet on sports teams but also analysts who try to optimize the game by looking into correlations in data and determining prominent factors of a winning team. In this report the problem is to determine which of the following factors determined by our team about the NBA can best predict the number of regular season wins.

The following is the list of factors:

-Number of All-Star Players (allstars)

-Average Age of Starting Lineup (age)

-Percentage of wins in the preseason (preseason)

-Number of wins from last season (lastwins)

-Average salary of players on the team (salary)

-Points per game (PPG)

-3-Pointers taken per game (PAG3)

-Opponent points per game (oppoints)

-Back-to-back games in a season (backtoback)

-Personal Fouls per game (pf)

-Team Value in billions of dollars (tv)

-Revenue per game in millions of dollars (rev)

 

Description of the Analysis Methods

The factors chosen to be included in the analysis are continuous variables which allows for the data set to be analyzed using multiple linear regression as opposed to analysis of variance. Additionally, the question of the problem involves predicting a team’s winning potential which would require a fitted regression line. The data collected for this analysis is from each team in the NBA from the 2015-16 season and is shown in Figure 1. A summary of the statistics for the response and 12 potential explanatory variables across the 30 teams (aka observations) is shown in Figure 2.

A common concern with multiple linear regression analyses is the potential of highly correlated explanatory variables which can result in “false negatives” with regard to the potential significance of parameters. To alleviate this concern, Figure 3 shows the Pearson Correlations between all of the variables, including the explanatory variable. For visual confirmation of the existence or lack of correlations between variables, Figure 4 shows a subset of the scatter plot matrix. SAS would not create the 13×13 grid of correlation scatter plots. The highest Pearson Correlation Coefficient is only 0.92 between team value and average revenue per game. If there appears to be an issue to multicollinearity in the parameter estimates in the regressions results, one of these two variable would most likely be eliminated to move the X’X matrix further from being singular. The absolute value of all other correlations are less than 0.6 which doesn’t create much concern of high correlations between the other explanatory variables.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig1.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig2.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig3.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig4.JPG)

Results

Diagnostic plots of the residuals for the full model are shown in Figure 5 with the residuals plotted against each of the explanatory variables in Figure 6.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig5.JPG)

The QQ plot is shown in the fit diagnostics plot. It suggests the data are approximately Normal because the fit is relatively linear, even though there is a slight s-shape in the QQplot.

The histogram of residuals is shown in the bottom left panel of the fit diagnostics plot. The data for the residuals of the wins looks relatively Normal.

There doesn’t appear to be violations of assumptions in any of the residuals plots.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig6.1.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig6.2.JPG)

In each of the residuals plots, we find that the variance appears to be constant. Although it’s difficult to judge the variance when there is one data point present at that extent of the explanatory variable. The residuals appears to be reasonably Normal. No real deviations can be found in these plots

From the leverage plot in the upper right of the Figure 6, there are three teams with unusual leverages.

After checking the assumptions and finding no blatant violations, the data was then used to determine the results of the multiple linear regression.

The results of the multiple linear regression with the full model are shown below in Figure 7. The ANOVA table shows that the explanatory variables chosen to be in the model are effective at predicting the number of wins as shown by the P-value < 0.0001. The table below this displays some statistics of the model such as the adjusted R-square value which claims that this model can explain about 96% of the variability in the amount of wins a team will have in a season. Additionally, the estimated standard deviation (Root MSE) is only 2.84 wins.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig7.1.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig7.2.JPG)

The last table in Figure 7 shows the estimates of the coefficients for the twelve explanatory variables in the linear model. Looking at the P-values for the significance tests (t-tests), it is clear that most of the factors are not individually well-suited factors, with all other variables included, to model a team’s performance over the whole season except for two: Points Per Game and Opponents points.

Below is the model for the full model equation to best predict the number of wins by an NBA team.

X1= ages; X2=lastwins; X3= preseason; X4= allstar; X5=salary; X6=PPG; X7=PAG3; X8=oppints X9= backtoback; X10= pf; X11= tv; X12 = rev;

Y(hat) = βo + β1X1 + β2X2 + β3X3 + β4X4 + β5X5 + β6X6 + β7X7 + β8X8 + β9X9 + β10X10 + β11X11 + β12X12

Y(hat) = 15.60488 + 0.24139X1 + 0.12403X2 + 1.25479X3 – 0.13042X4 – 0.00799X5 + 2.48723X6 – 0.17278X7 – 2.34036X8 + 0.37148X9 – 0.22553X10 + 0.37280X11 + 0.00393X12

R^2 = 0.9754

H0 : β1=β2=β3=β4=β5=β6=β7=β8=β9=β10=β11=β12=0

Ha:  β1≠β2≠β3≠β4≠ β5≠ β6≠ β7≠ β8≠ β9≠ β10≠ β11≠ β12≠ 0

F* = 56.13

Df = 12 and 17

P-value < 0.0001

Reject H0

This P-value means that we should reject the null hypothesis. The fact that we reject the null hypothesis means that at least one of these variables is significant in modeling that season’s wins, and therefore the data can be modeled by a linear relationship. By looking at the t-tests for each of the individual coefficients, Points Per Game and Opponents points are found significant even after fitting the other variables first.

Due to the fact that so many variables were being used and many of the variables obviously did not contribute to the model we found a reduced model to better explain the data. The model shown below is the model with the highest Adjusted R-Square. The best three models to represent the data based on their Adjusted R-Square are shown in Figure 8. The Adjusted R-Square function was used due to the fact that Adjusted R-Square adjusts the statistic based on the number of independent variables.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig8.JPG)

The best model when using Adjusted R-Square is the model with just age, last year’s wins, points per game, 3 pointers per game, opponent’s points per game and number of back to back games.

Comparing the estimated standard deviations between the two models, we see that the reduced model has a Root MSE of 2.49 while that of the full model is 2.85. The variation about the fitted line decreases when using the reduced model. Figure 9 shows these statistics as well as the parameter estimates for the two explanatory variables in this reduced model. Figure 10 and 11 show plots to allow for diagnostics of the regression and the residuals. The normal quantile (QQ) plot and the histogram of the residuals reveal a very normal residual distribution, however, in Figure 10, the residuals plotted against the explanatory variables show some signs of nonconstant variance. The variance of the wins tends to decrease as the PPG statistic increases.

![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig9.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig10.JPG)
![alt text](https://github.com/pamazing1515/Howtowin-NBA/blob/master/fig11.JPG)

Conclusions

After determining the problem to investigate, which is determining what factors contributed the most to the number of NBA 2015-2016 wins in the regular season, the data of twelve variables was ran with the multiple linear regression test. Once the full model was ran, the reduced model was created by selecting the model with the highest Adjusted R-Square. It was found that the most significant model consisted of age, last year wins, points per game, 3 pointer attempts per game, opponent points and back to back games. This model had an Adjusted R-Square of .9678 which is indicative of a strong model.

 

The variables selected in the reduced model also make sense in real world context. The model suggests that teams with older players, with more wins in the previous year, who scored more points, who attempted less 3 pointers, and who conceded less points were the teams that won the most games in the regular season. One interesting statistic found from the reduced model was a positive relationship between back to backs and wins. On the other hand variables such as number of all-stars, pre-season win percentages, team salary, personal fouls, team value and revenue are not as significant. Some of these factors not being as important are intuitive such as pre-season win percentage and personal fouls. Unexpectedly, the factors such as all-stars and team salary are not in the best reduced model. This indicates that a team cannot buy wins and that a more balanced team could have an advantage over teams with all-stars.

 



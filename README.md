# walmart-hurricane-project
Reflection Questions

**1. Data Quality Impact**
> Describe a specific data quality issue you encountered in the supplied data. How did your cleaning decision change the outcome of your analysis? What would have happened if you had not caught it?

The supplied data had a major issue with respect to cleaning revenue values that could be later analyzed. The sales data was unique from data sets we have worked with in the past in that there were rows with negative revenue, yet a positive quantity value. In the past, the cleaning convention had generally been to assume negative quantity values were returns, and their associated revenues would be correctly negative. We made the decision to also count those rows with positive quantities and negative revenues as returns. Given that there were 34 such rows, we made the assumption that there was not an error repeated 34 times, but rather 34 rows with negative revenues meant to represent returns. Importantly, we also added a flag for this unusual presentation, making such rows easily identifiable in the cleaned data set. Since this decision only impacted revenue, it did not affect our unit-based analysis. However, if we had chosen to drop the affected rows instead, the units would have been affected, potentially changing our findings. If we had not caught and flagged such rows, they would have been incorporated into further analysis without explanation. The abnormality of the positive quantity with negative revenue would have been forgotten as we continued to present findings down the line.

**2. ETL Trade-offs**
> You made choices about how to standardize SKUs, handle missing timestamps, and join weather data. Pick one decision and explain: what alternative approach could you have taken, and how might it have changed your results?

One decision we made was to consolidate all 4 Strawberry Pop-Tart SKUs into a single product, even through the product catalog lists POPTART-STRAW as a 6 pack and the other 3 SKUs were listed as 4 packs. Another approach would be to treat different pack sizes as different products. Using this alternative approach would have changed our result: the 4 pack group sold 2001 units during the surge week, which is less than bottled water (2240), so Pop-Tarts would have been ranked second to water instead of first. While this minute change would technically affect the ranking that would drive restocking decisions, the surge for Pop-Tarts would still be evident.

**3. Pipeline Trust**
> The Walmart CDO argued that the biggest risk is not the model — it is the pipeline. Based on your experience in this project, do you agree or disagree? What was the most fragile part of your data pipeline?

Based on our experience with the project, we would agree with the CDO because even a good analysis can produce misleading results if the underlying data is inconsistent or unreliable. The most fragile part of our pipeline was cleaning and combining data from different sources. We encountered inconsistent date formats, store IDs, category names, and duplicate SKUs, all of which had to be standardized before analysis. For example, we discovered that inventory levels dropped even for products with no recorded sales, showing that inventory data could not always be trusted to reflect purchasing behavior. These issues demonstrated that validating and cleaning the pipeline was essential to producing accurate conclusions.

**4. Business vs. Data**
> For Question 5 (board games), your team had to make a recommendation with imperfect data. How did you weigh statistical evidence against business risk? Would you have decided differently with more time or more data?

First, we were confident that there was a surge in board game sales, but we had to further investigate the scale of that surge. After further analysis, the +250% statistic was only a peak for a couple of days, while the surge over the week leading up to landfall was +160%. While from a business perspective, there is no risk of board games expiring or losing value by sitting on a shelf for extended periods of time, our recommendation still aimed to minimize overstocking. Therefore, we recommended that Walmart’s stock increase should reflect the surge over the full week before landfall, at 2.6x. If we had more time and data, such as reliable inventory data, we could more confidently recommend stocking more than 2.6x if that data showed that inventory was completely wiped out during the surge. Additionally, data from other storms could help improve the basis of our recommendation beyond the data from one storm surge.

**5. Team Collaboration**
> How did your team divide the work? What would you do differently if you had another week? What was the most valuable skill each team member contributed?

Our team randomly assigned the work equally to ensure that everyone had the same amount to complete. If we had another week, we would spend more time on the graphs and find additional correlations that would have a meaningful impact in future scenarios. Jackson worked on the cleaning for Q1 & Q2, Rushil did the API call for weather in Q3, Luke did the join for Q4, and Derek completed Q5. We all worked together on the final slideshow, putting the information we got from the our section together to put all of the information together.

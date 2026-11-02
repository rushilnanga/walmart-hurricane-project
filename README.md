# walmart-hurricane-project
Reflection Questions

**1. Data Quality Impact**
> Describe a specific data quality issue you encountered in the supplied data. How did your cleaning decision change the outcome of your analysis? What would have happened if you had not caught it?

The supplied data had a major issue with respect to cleaning revenue values that could be later analyzed. The sales data was unique from data sets we have worked with in the past in that there were rows with negative revenue, yet a positive quantity value. In the past, the cleaning convention had generally been to assume negative quantity values were returns, and their associated revenues would be correctly negative. We made the decision to also count those rows with positive quantities and negative revenues as returns. Given that there were 34 such rows, we made the assumption that there was not an error repeated 34 times, but rather 34 rows with negative revenues meant to represent returns. Importantly, we also added a flag for this unusual presentation, making such rows easily identifiable in the cleaned data set. Since this decision only impacted revenue, it did not affect our unit-based analysis. However, if we had chosen to drop the affected rows instead, the units would have been affected, potentially changing our findings. If we had not caught and flagged such rows, they would have been incorporated into further analysis without explanation. The abnormality of the positive quantity with negative revenue would have been forgotten as we continued to present findings down the line.

**2. ETL Trade-offs**
> You made choices about how to standardize SKUs, handle missing timestamps, and join weather data. Pick one decision and explain: what alternative approach could you have taken, and how might it have changed your results?

**3. Pipeline Trust**
> The Walmart CDO argued that the biggest risk is not the model — it is the pipeline. Based on your experience in this project, do you agree or disagree? What was the most fragile part of your data pipeline?

**4. Business vs. Data**
> For Question 5 (board games), your team had to make a recommendation with imperfect data. How did you weigh statistical evidence against business risk? Would you have decided differently with more time or more data?

**5. Team Collaboration**
> How did your team divide the work? What would you do differently if you had another week? What was the most valuable skill each team member contributed?

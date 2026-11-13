# Walmart Hurricane Project

This is for the class Data Science Systems (DS 2002) at the University of Virginia.

[Slide Deck](https://docs.google.com/presentation/d/1i889-i2Xc9Ope2ZDvVobRE-rad6hl-mf6GezBuDgRBs/edit?usp=sharing)

[Final Notebook](notebooks/final_notebook.ipynb)

## Reflection Questions

**1. Data Quality Impact**
> Describe a specific data quality issue you encountered in the supplied data. How did your cleaning decision change the outcome of your analysis? What would have happened if you had not caught it?

We noticed that there were many category names that meant the same thing (like groceries and grocery). We decided to merge them together under one name to not misrepresent the category magnitudes. Some things were using underscores instead of dashes which would also cause them to not register as the same name, so those were all normalized. If we hadn't done that, our numbers would have been much lower than they should have been.

**2. ETL Trade-offs**
> You made choices about how to standardize SKUs, handle missing timestamps, and join weather data. Pick one decision and explain: what alternative approach could you have taken, and how might it have changed your results?

I used the daily data from the weather. What I could have done instead is use the hourly data, and only aggregate the hours in which Walmart was actually open. This may have given better weather data that actually corresponds with what customers are dealing with when they do visit Walmart. I could potentially get higher correlations with sales data and weather data.

**3. Pipeline Trust**
> The Walmart CDO argued that the biggest risk is not the model — it is the pipeline. Based on your experience in this project, do you agree or disagree? What was the most fragile part of your data pipeline?

I definitely agree. The data pipeline was difficult to get right just because you cannot make that many assumptions about the data. At first, the date cleaning was not working well - it was actually returning NaT (not a time) for a ton of values silently and I didn't notice until later. Finding the solution took a little bit of time, but I eventually got it working. If I hadn't done that I wouldn't have been able to do any meaningful analysis.

**4. Business vs. Data**
> For Question 5 (board games), your team had to make a recommendation with imperfect data. How did you weigh statistical evidence against business risk? Would you have decided differently with more time or more data?
 
Statistical evidence helps provide a little bit more certainty, even if it's with imperfect data. But since it was so imperfect, I only suggested increasing board game stock by a small amount since we were really not so sure. With more data in future years, perhaps I would make a more forceful decision.

**5. Team Collaboration**
> How did your team divide the work? What would you do differently if you had another week? What was the most valuable skill each team member contributed?

Angela Choi (Siwon) did most of the cleaning and the SKU consolidation (Question 2) and the regional analysis (Question 4). Aidan did the weather API calls (Question 3) and the entertainment case (Question 5). We both contributed equally on Question 1, and the slidedeck was mostly put together by Siwon.

We had an extra week, so I don't think we would have done much differently besides asking the instructor more questions.

The most valuable skill for us...

Siwon - problem analysis and figuring out what to do with the data

Aidan - programming, visualizations, and figuring out how to get Python libraries to do what we want
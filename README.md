# Bootstrapping Regression Statistics

This assignment asks you to use the bootstrap technique we've discussed
to generate bootstrap statistics and compare those to the standard estimates
from R. The details are in `reg_boot.rmd`. Cheers!

When you submit your work, make sure to "knit" your RMD to an `.html` file and include that file in the repo you submit. (You can also knit to PDF and Word formats, which are great, but the HTML files are a bit easier for me to evaluate.) 

## Feedback

Add some jitter to that first plot. My modifications would be this: 
```
ggplot(d, aes(x = tenure, y = satisfaction, color = assigned_sex)) +
  geom_point(position=position_jitter(h=0.1),alpha=0.5) +
  labs(title = "Satisfaction vs Tenure by Assigned Sex",
       x = "Tenure",
       y = "Satisfaction") +
  theme_minimal()
```

Fun plot though. 

I'm not sure how much mean-centering tenure gets us here since a zero value can be intepreted as someone's first day of work. I'd definitely make a new column for it rather than overwriting the old one, though, since that change can't be reversed unless you store the mean value. But since you don't store it, you just have to write "who's _(sic)_ has an average tenure". Better to say "who has a tenure of XX, the average in the data set."

You conflate the male and tenure coefficients in that write-up.

Everything your bootstrapping is excellent.

You ask: 
> Should I use the 0.5 quantile from the bootstrap resample or the mean value from the resample for this comparison to the summary function results?
>

Great question. Most people use mean, though I tend to prefer the median (0.5 quantile). If the bootstrap replicate distribution is skewed, then I find the median more representative. 

You have a few issues above, but I'm going to call this complete because you do such a nice job on the main parts of the assignment. And you asked a good question!


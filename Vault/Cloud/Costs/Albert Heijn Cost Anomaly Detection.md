Calculate averages for specific scope (eg. application) and specific time frame (eg. weekdays) for some lookback period.

Calculate difference of current spend with that average

Anomaly defined as 
3 standard deviation difference and exceeding dynamic threshold 1 (lower threshold)
1.5 standard deviation difference and exceeding dynamic threshold 2 (high threshold)

How did you decide on these two definitions of an anomaly? Did you try some different definitions and figure out that this is best?

They were many discussions, this definition provides a lot of flexibility right now and works well. It could be extended to have a third category with anomalies, if needed. Or (more likely) they will start experimenting with machine learning/ai to find anomalies.

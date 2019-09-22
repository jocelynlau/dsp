[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```
#Set up
import scipy.stats

#Solution
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)

#Converted heights from feet/inches to centimeters
lower = 177.8
upper = 185.42

lower2 = dist.cdf(lower)
upper2 = dist.cdf(upper)

upper2-lower2
```

About 34.3% of the male US population is between 5'10" and 6'1".
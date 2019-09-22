[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
#Set up
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

#Solution
a = list(np.random.random(1000))

pmf_plot = thinkstats2.Pmf(a)
thinkplot.Pmf(pmf_plot)
thinkplot.Config(xlabel='Random numbers', ylabel='PMF')

cdf_plot = thinkstats2.Cdf(a)
thinkplot.Cdf(cdf_plot)
thinkplot.Config(xlabel='Random numbers', ylabel='CDF')
```

The distribution appears to be uniform based on the CDF plot which shows a straight diagonal line from the origin to (1,1).
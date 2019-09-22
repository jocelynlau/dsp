[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

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
resp = nsfg.ReadFemResp()

num_children = thinkstats2.Pmf(resp["numkdhh"], label = "observed")

def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

num_children_biased = BiasPmf(num_children,"biased")

thinkplot.PrePlot(2)
thinkplot.Pmfs([num_children, num_children_biased])
thinkplot.Config(xlabel='Number of children < 18', ylabel='PMF')

num_children.Mean()
num_children_biased.Mean()
```

Unbiased mean: 1.024
Biased mean: 2.404
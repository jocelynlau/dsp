[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```
#Set up
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

#Cohen's d calculation

def my_cohen_es(group1,group2,var):
    mean1, mean2 = group1[var].mean(), group2[var].mean()
    std1, std2 = group1[var].std(), group2[var].std()

    pooled_std = ((len(group1)*std1)+(len(group2)*std2))/(len(group1)+len(group2))
    return (mean1-mean2)/pooled_std

my_cohen_es(firsts,others,"totalwgt_lb")
```

Cohen's d for total weight: -0.0887

First babies had lower weight compared to other babies demonstrated by the negative Cohen's d. 
Compared to the effect size for pregnancy length, the effect size for total weight was:
- larger (larger absolute number)
- in the reverse direction (first babies had lower weight vs other babies but longer pregnancy length vs other babies).

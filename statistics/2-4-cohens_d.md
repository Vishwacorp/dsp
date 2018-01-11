
[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Run code below in the same directory as 'nsfg.py' and 'thinkstats2.py' files from the author.


```python
# import necessary modules
import numpy as np
import nsfg
import thinkstats2

# write function to calculate Cohen's d
def Cohens_d(group1, group2):
    mean1 = group1.mean()
    mean2 = group2.mean()
    
    var1 = group1.var()
    var2 = group2.var()
    
    len1 = len(group1)
    len2 = len(group2)
    
    pooled_var = (len1*var1 + len2*var2)/(len1 + len2)
    d = (mean1 - mean2)/np.sqrt(pooled_var)
    
    return d

# load data from pregnancy file and select records for live births
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

# use 'birthord' to separate firstborns from others
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

# get difference between means of newborn weight
diff_wgt_lb = firsts.totalwgt_lb.mean()-others.totalwgt_lb.mean()
perdiff_wgt_lb = abs(diff_wgt_lb/live.totalwgt_lb.mean())

# call 'Cohens_d()' function to calculate Cohen's d
# for weight of newborns using the 'totalwgt_lb' column
totalwgt_lb_cd = Cohens_d(firsts.totalwgt_lb, others.totalwgt_lb)
```


```python
# print out results
print('Difference in mean weights (lbs): ', '{:.3f}'.format(diff_wgt_lb))
print('% difference in mean weights: ', '{:.2%}'.format(perdiff_wgt_lb))
print("Cohen's d: ", '{:.3f}'.format(totalwgt_lb_cd))
```

    Difference in mean weights (lbs):  -0.125
    % difference in mean weights:  1.72%
    Cohen's d:  -0.089


The mean weight in pounds of first babies is 0.125 lbs lighter than other babies. This is less than 2% of a typical newborn's weight and therefore, not very significant. 

The Cohen's d value indicates that the difference in means is -0.089 standard deviations. While this value is larger than the Cohen's d value for pregnancy length, it is still small. 

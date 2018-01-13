
[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

**Exercise 5.1** In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use `scipy.stats.norm.cdf`.


```python
# import necessary modules
import scipy.stats
```


```python
# set up normal distribution model for male heights
mean = 178
stdev = 7.7
heights_norm_dist = scipy.stats.norm(loc=mean, scale=stdev)
```


```python
# to join the Blue Man Group, a male has to be 
# between 5'10" and 6'1" (177.8cm to 185.4cm)

min_height = 177.8
max_height = 185.4
perc_of_pop = heights_norm_dist.cdf(max_height) \
-heights_norm_dist.cdf(min_height)

print('Percentage between min & max heights: ', perc_of_pop)
```

    Percentage between min & max heights:  0.342094682946


**34.21%** of the US male population is between 5'10" and 6'1" and therefore qualifies to join the Blue Man Group.

[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> First babies are lighter than other babies, with a mean weight of 7.2 lbs vs 7.325 lbs, respectively. 
Cohen's d for the difference in means is -0.08867, meaning the difference in means between the two groups is -0.08867 standard deviations.

Python Code used:

def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
    
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()

CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)

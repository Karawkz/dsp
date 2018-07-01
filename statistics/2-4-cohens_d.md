[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

### Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s d to quantify the difference between the groups. How does it compare to the difference in pregnancy length?

    import numpy as np
    import nsfg

    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]
---
    
    firsts['totalwgt_lb'].mean(),others['totalwgt_lb'].mean()
(7.201094430437772, 7.325855614973262)

    firsts['totalwgt_lb'].std(),others['totalwgt_lb'].std()
(1.4205728777207374, 1.3941954762143138)

    firsts['totalwgt_lb'].var(),others['totalwgt_lb'].var()
(2.0180273009157768, 1.9437810258964572)

---

Cohen's D Formula

    def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.

    group1: Series or DataFrame
    group2: Series or DataFrame

    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d

    CohenEffectSize(firsts['totalwgt_lb'],others['totalwgt_lb'])
-0.088672927072602006

The mean weight of first babies is lower than that of other babies. The Cohen's D value is negative, which supports this. The value or size of the effect is also small (0.0887 standard deviations). 
The Cohen's D value of 0.0289 (0.0289 standard deviations) for pregnancy length is positive, which means that the mean pregnancy length for first babies is greater than that of other babies. However, the effect of pregnancy length compared to that of babies' weight is even smaller on first babies because the absolute Cohen's D value for pregnancy length is lower than that of babies' weight.


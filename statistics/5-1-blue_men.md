[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

    import scipy.stats
---

    mu = 178
    sigma = 7.7
    dist = scipy.stats.norm(loc=mu, scale=sigma)

    dist.mean(), dist.std()

    dist.cdf(mu-sigma)
---

1 inch = 2.54cm; 1 foot = 30.48cm
5'10 to cm
    b = 5*30.47 + 10*2.54

6'1 to cm
    t = 6*30.47 + 1*2.54

Proportion of people 5'10 and below:
    bottom = dist.cdf(b)

Proportion of people 6'1 and below:
    top = dist.cdf(t)

Percentage of people between 5'10 and 6'1
    ppl = top - bottom
    ppl*100
34.337490809959206
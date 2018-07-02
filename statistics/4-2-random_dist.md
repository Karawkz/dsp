[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

    import numpy as np
    import thinkstats2
    import thinkplot
    %matplotlib inline
---

    thousandrandoms = np.random.random(1000)

PMF

    pmf = thinkstats2.Pmf(thousandrandoms)
    thinkplot.Pmf(pmf,linewidth=0.4)
    thinkplot.Config(xlabel='Vals', ylabel='Freq')

![Image of Random PMF](https://github.com/Karawkz/dsp/blob/master/statistics/pmfrandom.png?raw=true)

CDF

    cdf = thinkstats2.Cdf(thousandrandoms)
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='Vals', ylabel='CDF')

![Image of Random CDF](https://github.com/Karawkz/dsp/blob/master/statistics/cdfrandom.png?raw=true)
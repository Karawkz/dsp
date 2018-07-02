[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)


### Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household.
### Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in
their household.
### Plot the actual and biased distributions, and compute their means.

    import numpy as np
    import nsfg
    import thinkstats2
    import thinkplot
    resp = nsfg.ReadFemResp()

Actual Distribution

    pmf = thinkstats2.Pmf(resp['numkdhh'], label='numkdhh')

Actual Mean

    pmf.Mean()

Bias Function

    def Bias(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)

    new_pmf.Normalize()
    return new_pmf

Bias Distribution

    bias = Bias(pmf, label='bias')

Bias Mean

    bias.Mean()

Plotted Distributions

    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, bias])
    thinkplot.Config(xlabel='No. of Children Under 18 Per Hh', ylabel='PMF')


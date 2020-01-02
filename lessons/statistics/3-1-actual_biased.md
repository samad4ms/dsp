[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>>

#Question 2 (3.1)
#load data
resp = nsfg.ReadFemResp()
numphh = resp['numkdhh']

#distributions of the variable
hist_numphh = thinkstats2.Hist(numphh)
pmf_numphh = thinkstats2.Pmf(hist_numphh, label = 'actual')
pmf_numphh_mean = pmf_numphh.Mean() #1.024205

#function to create biased pmf
def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        new_pmf.Normalize()
        return new_pmf

#run function
bias_pmf = BiasPmf(pmf_numphh, label = 'observed')
bias_pmf_mean = BiasPmf(pmf_numphh, label = 'observed').Mean() #1.918627

#plot actual and biased
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf_numphh, bias_pmf])
thinkplot.Show(xlabel='kids in household', ylabel='PMF')

[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> ANSWER: The CDF distribution is uniform but the PMF is not. Code below:

#generate 1000 random numbers, then compute CDF and PMF
nums = np.random.random(1000)
nums_cdf = thinkstats2.Cdf(nums)
nums_pmf = thinkstats2.Pmf(nums)

#plot CDF to see if uniform (it is)
thinkplot.Cdf(nums_cdf, label= 'CDF')
thinkplot.Show(xlabel='Num', ylabel='CDF')

#plot PMF to see if uniform (it is not)
thinkplot.Pmf(nums_pmf, label='PMF')
thinkplot.Show(xlabel='Num', ylabel='PMF', axis = [0,1,0,.002]) #arbitrary axis adjustment

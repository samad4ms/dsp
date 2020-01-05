[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
#create normal distribution with set parameters
dist = scipy.stats.norm(loc=187, scale=7.7)

#use cdf method to find cdf for 5'10 == 177.8cm
fiveten = dist.cdf(177.8) #0.4896

#find cdf for 6'1 == 185.4cm
sixone = dist.cdf(185.4) #0.8317

#the difference is the % of people between 5'10 and 6'1
diff = sixone-fiveten #0.342

final answer == 34.2%

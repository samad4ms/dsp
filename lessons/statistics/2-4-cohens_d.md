[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> MY ANSWER BELOW:

preg = nsfg.ReadFemPreg()

# First find live babies and keep only necessary columns
live = preg[preg.outcome == 1]
data = live[['pregordr', 'totalwgt_lb']]

# then select first babies and others
first_born = data[data.pregordr == 1]
not_first = data[data.pregordr != 1]

# create function to solve for cohens d

def CohensD(group1, group2):

    diff = first_born.mean() - not_first.mean()
    var1 = first_born.var()
    var2 = not_first.var()
    n1,n2 = len(first_born), len(not_first)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d

CohensD(first_born, not_first)['totalwgt_lb']

This function returns -0.06911936019885215 as the answer

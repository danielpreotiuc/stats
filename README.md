# Statistics scripts

Random statistics scripts I made.

### Partial correlation in Python

Simple partial correlation implementation. 

An implementation of the algorithm: [http://en.wikipedia.org/wiki/Partial_correlation#Using_linear_regression](http://en.wikipedia.org/wiki/Partial_correlation#Using_linear_regression)

The result is the partial correlation between X and Y while controlling for the effect of Z

Code is a modification of the one from [here]([https://gist.github.com/fabianp/9396204419c7b638d38f) (which is wrong) that also allows to set what variables you want to control for.

  pcorr(df,ind) 

Input:

df -  Pandas data frame and outputs a dataframe with a matrix of the Pearson correlation coefficients

ind - array of indices that serve as the control variables 

Sample usage:

  pcorr(df,[0,1]).to_csv('pcorr.csv',sep=',')

Requires:

numpy
pandas
scipy

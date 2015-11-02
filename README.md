# Statistics scripts

Random statistics scripts...

### Partial correlation in Python

Simple [partial correlation](http://en.wikipedia.org/wiki/Partial_correlation#Using_linear_regression) implementation. 

Takes as input a pandas dataframe and computes a matrix of correlations between all variables with a specified set (z) as controls.

Code is a correction of the one from [here](https://gist.github.com/fabianp/9396204419c7b638d38f), and it also allows to set which variables you want to control for. Code is tested against the R pcorr implementation.

```
pcorr(df,z)
```

Input:

df -  Pandas data frame and outputs a dataframe with a matrix of the Pearson correlation coefficients

z - array of indices of the variables to control for

Sample usage:

```
pcorr(df,[0,1]).to_csv('pcorr.csv',sep=',')
```

Requires:

numpy
pandas
scipy

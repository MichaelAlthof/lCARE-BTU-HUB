
[<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/banner.png" width="888" alt="Visit QuantNet">](http://quantlet.de/)

## [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/qloqo.png" alt="Visit QuantNet">](http://quantlet.de/) **LCARE_Index_Returns_Description** [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/QN2.png" width="60" alt="Visit QuantNet 2.0">](http://quantlet.de/)

```yaml

Name of Quantlet : LCARE_Index_Returns_Description

Published in : LCARE

Description : 'Provides descriptive statistics for the selected index return time series from 3
January 2005 to 31 December 2014 (2608 trading days): mean, median, minimum (Min), maximum (Max),
standard deviation (Std), skewness (Skew.) and kurtosis (Kurt.)'

Keywords : 'risk management, index, returns, plot, time-series, dax, ftse100, mean, median,
standard deviation, skewness, kurtosis'

See also : LCARE_Index_Returns

Author : Andrija Mihoci, Xiu Xu

Submitted : Sat, November 07 2015 by Andrija Mihoci and Xiu Xu

Datafile : DataIndices.dat

Input : DataIndices.dat

Output : LCARE_Index_Returns_Table

Example : Plots of selected index return time series

```


### MATLAB Code:
```matlab

clear all; clc;

data   = load('DataIndices.dat');
r_DAX  = diff(log(data(:, 1)));       % r_DAX daily data
r_FTSE = diff(log(data(:, 2)));       % r_FTSE daily data
r_SP   = diff(log(data(:, 3)));       % r_SP daily data

r                         = [r_DAX r_FTSE r_SP];
LCARE_Index_Returns_Table = [(mean(r))' (median(r))' (min(r))' (max(r))'...
                            (std(r))' (skewness(r))' (kurtosis(r))'];

save('LCARE_Index_Returns_Table', 'LCARE_Index_Returns_Table', '-ascii');

```

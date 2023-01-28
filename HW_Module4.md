---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.1
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# Written Report – 6.419x Module 4

<div class="author"><b>Name:</b> username</div>

```{code-cell}
:tags: ["remove-input"]
import numpy as np
import pandas as pd
from datetime import date
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression as LinReg
from sklearn.model_selection import train_test_split
```

## Problem 2.1

*(3 points) Plot the periodic signal . (Your plot should have 1 data point for each month, so 12 in total.) Clearly state the definition the , and make sure your plot is clearly labeled.*

**Solution:**


<br>

## Problem 2.2

*(2 points) Plot the final fit $F_n(t_i) + P_i$. Your plot should clearly show the final model on top of the entire time series, while indicating the split between the training and testing data.*

**Solution:**


<br>

## Problem 2.3

*(4 points) Report the root mean squared prediction error $\text{RMSE}$ and the mean absolute percentage error $\text{MAPE}$ with respect to the test set for this final model. Is this an improvement over the previous model $F_n(t_i)$ without the periodic signal? (Maximum 200 words.)*

**Solution:**


<br>

## Problem 2.4

*(3 points) What is the ratio of the range of values $F$ of to the amplitude of $P_i$ and the ratio of the amplitude $P_i$ of to the range of the residual $R_i$ (from removing both the trend and the periodic signal)? Is this decomposition of the variation of the CO$_2$ concentration meaningful? (Maximum 200 words.)*

**Solution:**


<br>

## Problem 3.1

*(4 points) Consider the $\mathrm{MA}(1)$ model,
$$ X_t = W_t + \theta W_{t-1} $$,
where $\{W_t\} \sim W \sim \mathcal N(0,\sigma^2)$. Find the autocovariance function of $\{X_t\}$.
Include all important steps of your computations in your report.*

**Solution:**


<br>

## Problem 3.2

*(4 points) Consider the $\mathrm{AR}(1)$ model,
$$ X_t = \phi X_{t-1} + W_t $$,
where $\{W_t\} \sim W \sim \mathcal N(0,\sigma^2)$. Suppose $|\phi| < 1$. Find the autocovariance function of $\{X_t\}$. (You may use, without proving, the fact that $\{X_t\}$ is stationary if $|\phi|<1$.)
Include all important steps of your computations in your report.*

**Solution:**


<br>

## Problem 5.1

*(9 points) Repeat the model fitting and evaluation procedure from the previous page for the monthly inflation rate computed from $\text{CPI}$.

**Solution:**

- (1 point) Description of how you compute the monthly inflation rate from $\text{CPI}$ and a plot of the monthly inflation rate. (You may choose to work with log of the CPI.)

- (2 points) Description of how the data has been detrended and a plot of the detrended data.

- (3 points) Statement of and justification for the chosen $\mathrm{AR}(p)$ model. Include plots and reasoning.

- (3 points) Description of the final model; computation and plots of the 1 month-ahead forecasts for the validation data. In your plot, overlay predictions on top of the data.

<br>

## Problem 5.2

*(3 points) Which $\mathrm{AR}(p)$ model gives the best predictions? Include a plot of the $\text{RMSE}$ against different lags $p$ for the model.*

**Solution:**


<br>

## Problem 5.3

*(3 points) Overlay your estimates of monthly inflation rates and plot them on the same graph to compare. (There should be 3 lines, one for each datasets, plus the prediction, over time from September 2013 onward.)*

**Solution:**


<br>

## Problem 6.1

*(4 points) Plot the cross correlation function between the $\text{CPI}$ and $\text{BER}$ inflation rate, by which find , i.e., the lag between two inflation rates. (As only one external regressor term is involved in the model, we only consider the peak in the CCF plot.)*

**Solution:**


<br>

## Problem 6.2

*(3 points) Fit a new $\text{AR}$ model to the $\text{CPI}$ inflation rate with these external regressors and the most appropriate lag. Report the coefficients.*

**Solution:**

*Python Tip:* You may use sm.tsa.statespace.SARIMAX.

<br>

## Problem 6.3

*(3 points) Report the mean squared prediction error for 1 month ahead forecasts.*

**Solution:**


<br>

## Problem 6.4

*(5 points) What other steps can you take to improve your model from part III? What is the smallest prediction error you can obtain? Describe the model that performs best. You might consider including MA terms, adding a seasonal AR term, or adding multiple daily values (or values from different months) of $\text{BER}$ data as external regressors.*

**Solution:**


<br>

## Includes

The code below must be run before any code above.

```
import numpy as np
import pandas as pd
from datetime import date
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression as LinReg
from sklearn.model_selection import train_test_split
```

## Citations


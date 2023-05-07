Download Link: https://assignmentchef.com/product/solved-machinelearning-assignment-2
<br>
Complete each problem below and print to pdf. Submit the pdf.You will need to work with the three datasets attached to this assignment:• poverty.csv• poverty_2.csv• real_estate.csv1 Problem 1: Univariate Linear Regression1.1 1) import the libraries you will need:

/usr/local/lib/python3.7/dist-packages/statsmodels/tools/_testing.py:19: FutureWarning: pandas.util.testing is deprecated. Use the functions in the public API at pandas.testing instead. import pandas.util.testing as tm1.2 2) Import the date poverty.csv dataset

&lt;IPython.core.display.HTML object&gt;Saving real_estate.csv to real_estate (4).csv1.3 3) Print the dataset indexed upon the location column.

[ ]: PovPct Brth15to17 Brth18to19 ViolCrime TeenBrthLocationAlabama 20.1 31.5 88.7 11.2 54.5Alaska 7.1 18.9 73.7 9.1 39.5Arizona 16.1 35.0 102.5 10.4 61.2Arkansas 14.9 31.6 101.7 10.4 59.9California 16.7 22.6 69.1 11.2 41.1Colorado 8.8 26.2 79.1 5.8 47.0Connecticut 9.7 14.1 45.1 4.6 25.8Delaware 10.3 24.7 77.8 3.5 46.3District_of_Columbia 22.0 44.8 101.5 65.0 69.1Florida 16.2 23.2 78.4 7.3 44.5Georgia 12.1 31.4 92.8 9.5 55.7Hawaii 10.3 17.7 66.4 4.7 38.2Idaho 14.5 18.4 69.1 4.1 39.1Illinois 12.4 23.4 70.5 10.3 42.2Indiana 9.6 22.6 78.5 8.0 44.6Iowa 12.2 16.4 55.4 1.8 32.5Kansas 10.8 21.4 74.2 6.2 43.0Kentucky 14.7 26.5 84.8 7.2 51.0Louisiana 19.7 31.7 96.1 17.0 58.1Maine 11.2 11.9 45.2 2.0 25.4Maryland 10.1 20.0 59.6 11.8 35.4Massachusetts 11.0 12.5 39.6 3.6 23.3Michigan 12.2 18.0 60.8 8.5 34.8Minnesota 9.2 14.2 47.3 3.9 27.5Mississippi 23.5 37.6 103.3 12.9 64.7Missouri 9.4 22.2 76.6 8.8 44.1Montana 15.3 17.8 63.3 3.0 36.4Nebraska 9.6 18.3 64.2 2.9 37.0Nevada 11.1 28.0 96.7 10.7 53.9New_Hampshire 5.3 8.1 39.0 1.8 20.0New_Jersey 7.8 14.7 46.1 5.1 26.8New_Mexico 25.3 37.8 99.5 8.8 62.4New_York 16.5 15.7 50.1 8.5 29.5North_Carolina 12.6 28.6 89.3 9.4 52.2North_Dakota 12.0 11.7 48.7 0.9 27.2Ohio 11.5 20.1 69.4 5.4 39.5Oklahoma 17.1 30.1 97.6 12.2 58.0Oregon 11.2 18.2 64.8 4.1 36.8Pennsylvania 12.2 17.2 53.7 6.3 31.6Rhode_Island 10.6 19.6 59.0 3.3 35.6South_Carolina 19.9 29.2 87.2 7.9 53.0South_Dakota 14.5 17.3 67.8 1.8 38.0Tennessee 15.5 28.2 94.2 10.6 54.3Texas 17.4 38.2 104.3 9.0 64.4Utah 8.4 17.8 62.4 3.9 36.8Vermont 10.3 10.4 44.4 2.2 24.2Virginia 10.2 19.0 66.0 7.6 37.6Washington 12.5 16.8 57.6 5.1 33.0West_Virginia 16.7 21.5 80.7 4.9 45.5Wisconsin 8.5 15.9 57.1 4.3 32.3Wyoming 12.2 17.7 72.1 2.1 39.91.4 4) Get useful descriptive statistial data on the dataset.Hint: this is a single line, data._____[ ]: poverty.describe()[ ]: PovPct Brth15to17 Brth18to19 ViolCrime TeenBrthcount 51.000000 51.000000 51.000000 51.000000 51.000000mean 13.117647 22.282353 72.019608 7.854902 42.243137std 4.277228 8.043499 18.975563 8.914131 12.318511min 5.300000 8.100000 39.000000 0.900000 20.00000025% 10.250000 17.250000 58.300000 3.900000 33.90000050% 12.200000 20.000000 69.400000 6.300000 39.50000075% 15.800000 28.100000 87.950000 9.450000 52.600000max 25.300000 44.800000 104.300000 65.000000 69.1000001.5 5) Print the columns

Index([‘PovPct’, ‘Brth15to17’, ‘Brth18to19’, ‘ViolCrime’, ‘TeenBrth’], dtype=’object’)1.6 6) Create a regression line based upon the dependent and independent variables:PovPct Brth18to19In this step only create a scatterplot of the two variables, simply plotting the data.Note: The variable PovPct is the percent of a state’s population in 2000 living in households with incomes below the federally defined poverty level.[ ]: plt.scatter(poverty.PovPct, poverty.Brth18to19)[ ]: &lt;matplotlib.collections.PathCollection at 0x7efc09f48d50&gt;

1.7 7) Lets create a new variable, x1, as well as the results variable:Example would be 1. x1 = sm.add_constant(x) 2. results = sm.OLS(y, x1).fit() 3. results.summary() This gives you the OLS Regression results, the coefficients table, and some additional tests. The data that you are interested in is the coefficient values. This is the value for the constant you created is b0, and birth19to19 is b1 in the regression equation.[ ]: x1 = sm.add_constant(poverty.PovPct)/usr/local/lib/python3.7/dist-packages/statsmodels/tsa/tsatools.py:117:FutureWarning: In a future version of pandas all arguments of concat except for the argument ‘objs’ will be keyword-onlyx = pd.concat(x[::order], 1)

[ ]: &lt;class ‘statsmodels.iolib.summary.Summary’&gt; “””OLS Regression Results==============================================================================Dep. Variable: Brth18to19 R-squared: 0.422Model: OLS Adj. R-squared: 0.410Method: Least Squares F-statistic: 35.78Date: Thu, 17 Feb 2022 Prob (F-statistic): 2.50e-07Time: 02:35:21 Log-Likelihood: -207.98No. Observations: 51 AIC: 420.0Df Residuals: 49 BIC: 423.8Df Model: 1Covariance Type: nonrobust============================================================================== coef std err t P&gt;|t| [0.025 0.975]—————————————————————————–const 34.2124 6.641 5.151 0.000 20.866 47.559 PovPct 2.8822 0.482 5.982 0.000 1.914 3.850==============================================================================Omnibus: 1.175 Durbin-Watson: 2.161Prob(Omnibus): 0.556 Jarque-Bera (JB): 0.988Skew: 0.088 Prob(JB): 0.610Kurtosis: 2.341 Cond. No. 45.1==============================================================================Warnings:[1] Standard Errors assume that the covariance matrix of the errors is correctly specified. “””1.8 8) Taking the coeffient values for the new constant and the Y variable, create a scatterplot:e.g. yhat = 0.1464*x + 0.25712 fig = plt.plot(x, yhat, lw=4, c=’red’, label = ’regression line’)[ ]: plt.scatter(poverty.PovPct, poverty.Brth18to19) plt.plot([0,25],[34.2124,2.8822*25+34.2124], color=”magenta”)[ ]: [&lt;matplotlib.lines.Line2D at 0x7fb63c15ab10&gt;]

2 Problem 2: Implement code from lecture2.1 1) Perform linear regression using the normal equation, as done in slides.

[ ]: [&lt;matplotlib.lines.Line2D at 0x7fb641086710&gt;]

[2. 93813808]])[ ]: plt.plot(X,y,”b.”) plt.plot([0,2],[theta_best[0],theta_best[1]*2+theta_best[0]], color=”magenta”)[ ]: [&lt;matplotlib.lines.Line2D at 0x7fb63be61190&gt;]

2.2 2) Perform linear regression using Scikit-Learn, as done in the slides.

[ ]: (array([4.52769162]), array([[2.93813808]]))

/usr/local/lib/python3.7/dist-packages/numpy/core/shape_base.py:65:VisibleDeprecationWarning: Creating an ndarray from ragged nested sequences (which is a list-or-tuple of lists-or-tuples-or ndarrays with different lengths or shapes) is deprecated. If you meant to do this, you must specify ‘dtype=object’ when creating the ndarray. ary = asanyarray(ary)[ ]: [&lt;matplotlib.lines.Line2D at 0x7fb63bf92d50&gt;]

3 Problem 3: Multivariate Linear RegressionIn this problem we will continue using the poverty dataset. Do poverty and violent crimes affect teen pregnancy?3.1 1) import the libraries you will need: numpy pandas matplotlab.pyplot statsmodels.api

3.2 2) Import the dataset, poverty_2.csv, and print it.

[ ]: PovPct ViolCrime TeenBrth0 20.1 11.2 54.51 7.1 9.1 39.52 16.1 10.4 61.23 14.9 10.4 59.94 16.7 11.2 41.15 8.8 5.8 47.06 9.7 4.6 25.8

7 10.3 3.5 46.38 22.0 65.0 69.19 16.2 7.3 44.510 12.1 9.5 55.711 10.3 4.7 38.212 14.5 4.1 39.113 12.4 10.3 42.214 9.6 8.0 44.615 12.2 1.8 32.516 10.8 6.2 43.017 14.7 7.2 51.018 19.7 17.0 58.119 11.2 2.0 25.420 10.1 11.8 35.421 11.0 3.6 23.322 12.2 8.5 34.823 9.2 3.9 27.524 23.5 12.9 64.725 9.4 8.8 44.126 15.3 3.0 36.427 9.6 2.9 37.028 11.1 10.7 53.929 5.3 1.8 20.030 7.8 5.1 26.831 25.3 8.8 62.432 16.5 8.5 29.533 12.6 9.4 52.234 12.0 0.9 27.235 11.5 5.4 39.536 17.1 12.2 58.037 11.2 4.1 36.838 12.2 6.3 31.639 10.6 3.3 35.640 19.9 7.9 53.041 14.5 1.8 38.042 15.5 10.6 54.343 17.4 9.0 64.444 8.4 3.9 36.845 10.3 2.2 24.246 10.2 7.6 37.647 12.5 5.1 33.048 16.7 4.9 45.549 8.5 4.3 32.350 12.2 2.1 39.93.3 3) We need to normalize the input variables.

3.4 4) Split the data into input variables, X, and the output variable, Y.

3.5 5) Graph the dataset with a seed of 42.

3.6 6) Implement Gradient Descent.This section has be provided. Please run and understand the code.

iteration : 0 loss : 0.14248615838353396 iteration : 100 loss : 0.005841062708110685 iteration : 200 loss : 0.005374637890296291 iteration : 300 loss : 0.005059239296919674 iteration : 400 loss : 0.0048406904218634165

[ ]: array([[0.41375839],[0.26569717],

3.7 7) Implement Stochastic Gradient Descent. Please run.

iteration : 0 loss : 0.0066577245043739405 iteration : 100 loss : 0.003102327706993443 iteration : 200 loss : 0.002532377208293092 iteration : 300 loss : 0.0023333911770596814 iteration : 400 loss : 0.0022626837845736957

4 Problem 4, predict house price.• import real_estate.csv• Are there any null values in the dataset? Drop any missing data if exist.• Create X as a 1-D array of the distance to the nearest MRT station, and y as the housing price• What is the number of samples in the data set? To do this, you can look at the “shape” of X and y• Split the data into train and test sets using sklearn’s train_test_split, with test_size = 1/3• Find the line of best fit using a Linear Regression and show the result of coefficients and intercept (you can use sklearn’s linear regression)• Using the predict method, make predictions for the test set and evaluate the performance (e.g., MSE or other metrics).

[4]: X1 transaction date … Y house price of unit areaNo …1 2012.917 … 37.92 2012.917 … 42.23 2013.583 … 47.34 2013.500 … 54.85 2012.833 … 43.1.. … … …410 2013.000 … 15.4411 2012.667 … 50.0412 2013.250 … 40.6413 2013.000 … 52.5414 2013.500 … 63.9[414 rows x 7 columns]

[5]: X1 transaction date … Y house price of unit areaNo …1 2012.917 … 37.92 2012.917 … 42.23 2013.583 … 47.34 2013.500 … 54.85 2012.833 … 43.1.. … … …410 2013.000 … 15.4411 2012.667 … 50.0412 2013.250 … 40.6413 2013.000 … 52.5414 2013.500 … 63.9

/usr/local/lib/python3.7/dist-packages/sklearn/base.py:451: UserWarning: X does not have valid feature names, but PolynomialFeatures was fitted with feature names“X does not have valid feature names, but”[109]: &lt;matplotlib.collections.PathCollection at 0x7f578280b050&gt;

/usr/local/lib/python3.7/dist-packages/sklearn/base.py:451: UserWarning: X does not have valid feature names, but PolynomialFeatures was fitted with feature names“X does not have valid feature names, but”[112]: 73.4172288261123

/usr/local/lib/python3.7/dist-packages/sklearn/base.py:451: UserWarning: X does not have valid feature names, but PolynomialFeatures was fitted with feature names“X does not have valid feature names, but”[113]: 72.16393207172295

Quartic has the least squared error, got larger for 5 or 6 powered, MSE is 72.1639

Mounted at /content/drive/WARNING: apt does not have a stable CLI interface. Use with caution in scripts.WARNING: apt does not have a stable CLI interface. Use with caution in scripts. Extracting templates from packages: 100%[ ]: <img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/04/331.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/04/331.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>
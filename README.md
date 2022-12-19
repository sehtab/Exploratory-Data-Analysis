# Exploratory-Data-Analysis

# Objective:

The objective of this repository is to discuss several technics of Exploratory data Analysis..

# Approaches

At first, necessary libraries are imported. Sample data are implemented to make dataframe to perform univatiate and multivariate statistical analysis.

# Datasets

For this project insurance.csv and housing_full.csv are used..

# Results:

Results are generated with several libraries and accuracy is compared with several algorithm like OLS.

# Challenges

For this repository several stat library is not working.

# Planned Work

At first, necessarry dependencies are called. Then necessary function are called for operation. Here are the description:

1. For statistical description of a dataframe:      df.describe()

2. To get the dimension of a df:                    df.shape

3. to get the name of the columns:                  df.columns

4. To count the elements of a column:               df.age.count()

5. To get unque values in a column:                 df.age.nunique()

6. To get null values in columns:                   df.isnull().sum()

7. To get univariate statistics:                    df.charges.min() , df.charges.max(), df.charges.quantile(0.25), df.charges.quantile(0.5), 
                                                    df.charges.mean(), df.charges.median(), df.charges.mode(), df.charges.std(), np.std(df.chrges, ddof=1)
                                                    
8. To get skew and kurtosis:                        from scipy.stats import kurtosis, skew , print(f' skew: {skew(df.charges, bias=False)}') 
                                                    print(f' kurtosis: {kurtosis(df.charges, bias=False)}'), df.charges.skew(), df.charges.kurt()
                                                    
9. To get distribution plot:                        import seaborn as sns,  sns.distplot(df.charges, label='charges') 

10. To get correlation:                             np.corrcoef(g1,g2), df.corr()

11. To get Correlation & P value:                   from scipy import stats, r, p = stats.pearsonr(df.charges, df.age), print(r), print(p)

12. To get sample data from a column:               df.sample(50)

13. to get linear regression in a plot:             m,b,r,p, err = stats.linregress(df.age, df.charges)

14. To get heteroscedasticity:                      from statsmodel.stats.diagonostic import het_breuschpagan, from statsmodel.stats.diagonostic import het_white,
                                                    from statsmodel.formula.api import ols, model = ols(formula='charges-age', data=df).fit(),
                                                    white_test = het_white(model.resid,model.model.exog), breuchpagan_test = het_breuschpagan(model.resid, model.model.exog)
                                                    
15. to get jointplot:                               sns.jointplot(x='age', y = 'charges', data=df)

16. To get pairplot:                                sns.pairplot(df)

17. to get a 3D plot:                              from mpl_toolkits.mplot3d import Axes3D, fig= plt.figure(), three_d_plot= Axes3D(fig),                    three_d_plot.scatter(df.age,df.bmi, df.charges)   

18. to get 3D plot:                               import plotly.express as px, fig=px.scatter_3d(df,x='age',y='charges', z='bmi', color='smoker', symbol='sex',           size='children), fig.show()

19. to get histogram:                             sns.histplot(data=df,x='charges', hue='sex', kde=True)

20.to get ttest:                                  stats.ttest_ind[smoker_y['chrges'], smoker_n['charges']], stats.f_oneway(*grouped_values)

21. to get barplot:                              viz = sns.barplot(x=df['education'], y=df['Age'], hue=df['Purchased Bike']), plt.xticks(rotation=25), plt.show()

22. to get categorical plot:                     viz= sns.catplot(data=df, x='Education',y='Age',hue='Purchased Bike',col='Home Owner'), viz.set_xticklabels(rotation=25),
                                                 plt.show()
                                                 
23. to get Tukeyhsd:                             from statmodels.stats.multicomp import MultiComparison, mc=MultiComparison(df['Purchased bike'],df["Education"]), 
                                                 print(mc.tukeyhsd())
                                                 
24. to get ols:                                   import statsmodels.api as sm, model=sm.OLS(y,x),results=model.fit(),print(results.summary())

25.for normal dist. of target:                    np.log(df.charges)

26.extract r^2:                                 from sklearn.linear_model import LinearRegression, r_sq= LinearRegression().fit(x,y).score(x,y)

27. VIF:                                         1/(1 - r_sq)




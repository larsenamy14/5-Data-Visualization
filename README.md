# 5-Data-Visualization

## Step 1: Import modules
In this exercise we are using matplotlib, pandas, and scipy

## Step 2: Merge data
Use the function pd.merge to merge datasets into a single data frame

Count number of unique entries using set() and len()

## Step 3: Clean data
Find duplicate value using .duplicated(subset=[ , ])][ ].unique().

Remove duplicate value using .loc

## Step 4: Create summary statistics dataframe
Calculate mean, median, variance, standard deviation, and standard error

Combine data into single data frame

## Step 5: Create charts to visualize data
Create bar charts using (1) dataframe.plot(kind="bar") and (2) plt.bar(x, y)

Create pie charts using (1) dataframe.plot(kind="pie") and (2) plt.pie(x, y)

## Step 6: Quartiles, Outliers and Boxplots

Group data by Mouse ID and filter by max Timepoint

Use .reset_index to create new dataframe

Merge data with original clean dataframe to find the tumor volume at the max Timepoints

Use a for loop to calculate the IQR values to find potential outliers
    quartiles = tumor_vol.quantile([0.25, 0.5, 0.75])
    lower_q = quartiles[0.25]
    upper_q = quartiles[0.75]
    iqr = upper_q - lower_q

Potential outliers will be below lower bound and above upper bound
    lower_bound = lower_q - 1.5 * iqr
    upper_bound = upper_q + 1.5 * iqr
    
Plot the boxplot using dataframe.boxplot

## Step 7: Create lines and scatter plots
Filter data down to selected regimen using .loc and select a random Mouse ID

Plot data using plt.plot(df["Timepoint"], df["Tumor Volume"])

Calculate average tumor volume for each Mouse ID on the Capomulin regimen

Merge data to find the weight of the specific Mouse ID

Plot data using plt.scatter(avg_df["Weight"], avg_df["Avg Tumor Volume"])

## Step 8: Correlation and Regression
Use st.pearsonr to calculate the correlation coefficient between mouse weight and tumor volume

Calculate the linear regression model using (slope, intercept, rvalue, pvalue, stderr) = st.linregress

Plot the regression line

## Step 9: Final Analysis
Ketapril had the largest average tumor volume to treat. 

Infubinol was the only treatment with potential outliers. 

As weight of the mouse in the Capomulin treatment group increased, the average tumor volume also increased.

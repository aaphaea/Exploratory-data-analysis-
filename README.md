# EDA-
An Exploratory data analysis for a bank to help them predict who is gonna get churned so they can proactively go to the
customer to provide them better services and turn customer's decisions in the opposite direction.

LIBRARIES USED :
NumPy: The numpy library provides support for numerical operations and arrays in Python.
Pandas: The Pandas library is used for data manipulation and analysis. It provides powerful data structures, such as DataFrames, to work with structured data.
Seaborn: The Seaborn library is built on top of Matplotlib and provides a high-level interface for creating informative and visually appealing statistical graphics.
Matplotlib: The Matplotlib library is a powerful plotting tool for creating various types of visualizations.
Warnings: The warnings.filterwarnings('ignore') imports the `warnings` module and uses filterwarnings() function to ignore any warning messages that may occur during the code execution.
sns.set(color_codes=True): This sets the default color palette in Seaborn to use color codes. It affects the color scheme of Seaborn plots.

1. Display a sample of five rows of the data frame :

The .head() function returns the first n rows for the object based on position.

2. Check the shape of the data (number of rows and columns) :

The .shape() function returns a tuple containing the number of rows and 
columns in the DataFrame. The first element of the tuple, shape[0], represents 
the number of rows while the second element shape[1] represents the number of 
columns.

3. Check the percentage of missing values in each column of the 
data frame :

.isnull() checks for missing values in each cell of the DataFrame 
and returns a Boolean DataFrame where `True` indicates a 
missing value. 
By applying the mean() function to the Boolean DataFrame, we 
get the proportion of missing values for each column. 
Multiplying it by 100 gives us the percentage of missing values. 
The resulting missing percentages variable will be a Series object 
where the column names are the index, and the corresponding 
values are the percentages of missing values in each column.

4. Check if there are any duplicate rows :

.duplicated() checks each row of the DataFrame and returns a 
Boolean Series where True indicates a duplicate row.
By applying the any() function to the Boolean Series, we check if 
there are any True values, indicating the presence of duplicate 
rows.
The resulting output will be `True` if there are any duplicate rows 
in the DataFrame and `False` otherwise.

5. Check the distribution of the Customer_Age column. Check the basic 
statistics like mean, median, and standard deviation of the age column :

To check the distribution of any column in a DataFrame, you can use 
the hist() function from Matplotlib or the distplot() function from 
Seaborn. 
sns.distplot() creates a histogram and an estimated probability density 
function for the values in the specified column, using the Seaborn 
library

6. Plot 2 box plots and 2 pie charts :

To plot a pie chart for a given column in a Pandas DataFrame, you can 
use the value_counts () function to calculate the frequency of each 
unique value in the column.
.value_counts () calculate the frequency of each unique value in the 
'column_name' column and stores the result in `column_counts`.
The plt.pie () function creates the pie chart column_counts are passed 
as the first argument, and `labels` are set to `column_counts. index` to 
use the unique values from 'column_name' as labels. 
The `autopct` parameter formats the percentage values displayed on 
each slice.
The plt. axis('equal') line ensures that the pie chart is displayed as a 
circle.
The plt. title () function adds a title to the plot.
Finally, plt. show () is called to display the pie chart.

7. Plot a Boxplot of Total_Revolving_Bal and Card_Category by 
characterizing with Attrition_Flag :

This code creates a box plot using seaborn, where the x-axis represents 
the 'Total_Revolving_Bal' variable, the y-axis represents the 
'Card_Category' variable, and the boxes are differentiated by the 
'Attrition_Flag' variable. The box colors are specified using the 
`box_colors` list, and the whisker color is set to black. The plot is 
labeled, titled, and a legend is added before displaying it.

9. Plot a percentage segment bar graph between Education_Level 
and Attrition_Flag of the customers :

In this code, data. groupby('column1’) 
['column2'].value_counts(normalize=True)
. unstack () groups the data by 'column1' and 'column2', calculates the 
normalized value counts, and rearranges it into a DataFrame format.
Then, the plot () function is called on the resulting DataFrame with 
kind='bar' to create the percentage segment bar graph. 
The `stacked=True` parameter ensures that the bars are stacked on top 
of each other.
The plt. title (), plt. xlabel (), and plt. ylabel() functions are used to set 
the title, x-label, and y-label of the plot, respectively.
The plt. legend () function sets the legend for the different segments, 
using the values in 'column2', and positions it in the upper right corner.
Finally, plt. show () is called to display the plot.

9.Drop CLIENTNUM column. Make a sub data frame which consists of 
all the numerical columns (i.e.int64, float64) along with the 
Attrition_Flag column. Plot a clear heatmap to view the correlation using 
seaborn :

.drop ('column_name', axis=1) is used to drop the specified column from the 
DataFrame df. The 'column_name' parameter represents the name of the 
column you want to drop.
The axis=1 parameter is used to indicate that we want to drop a column. 
Setting axis=0 would drop a row instead.
data. select_dtypes (include= ['int64', 'float64']) filters the DataFrame
to include only the columns with data types int64 and float64, creating 
a sub DataFrame with only numerical columns.
The copy () method is called on the numerical DataFrame to create a 
deep copy, ensuring that any modifications made to it do not affect the 
original DataFrame.
Next, numerical_column['existing_column'] = data['existing_column'] 
adds the existing column from the original DataFrame df to the 
numerical DataFrame numerical_column.
The resulting numerical_column DataFrame will contain all the 
numerical columns along with the existing column from the original 
DataFrame.

10.Plot a boxplot for the Credit_Limit column and check if it contains 
any outlier or not :

To check if the parameter contains any outliers, you can visually inspect 
the boxplot. Outliers are usually represented as individual points beyond 
the whiskers of the boxplot. Any points outside the whiskers can be 
considered potential outliers. Keep in mind that the presence of outliers 
depends on the distribution and characteristics of the data.
As we can see above the boxplot for the Credit_Limit column does 
contain outliers.

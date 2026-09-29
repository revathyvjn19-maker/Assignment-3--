# Assignment-3--
Module End Assignment 1_Excel  - Healthcare Analysis and Insights
Healthcare Data Analysis and Insights- Solution

# Data Cleaning: 
* Check for the number of missing values marked with '?' in each column of the “Medical Examinations” Table and "Hospitalization Details" Table.
The number of missing values was found using a PivotTable.and “COUNTIF” function

Syntax **=COUNTIF(Table1[Customer ID],"?")**
* Fill in the missing values of ‘month’ with Sep and ‘year’ with its average rounded to the nearest integer.
Missing value of months replace with Sep -

Syntax **=IF(C2="?","Sep",[@month])**

Missing value of Year replaced with Average of year Syntax

**=IF([@year]="?","1983",[@year])**

*	Determine the most frequently occurring values in the ‘smoker’, 'Hospital tier' and 'City tier' columns, and fill in the missing values accordingly.
The most frequently occurring values were found using a PivotTable.

Smoker syntax **=IF([@smoker2]="?","no",[@smoker2])**

Hospital tier syntax **=IF([@[Hospital tier]]="?","tier - 2",[@[Hospital tier]])**

City tier syntax **=IF([@[City tier]]="?","tier - 2",[@[City tier]])**

* If any 'State ID' values are missing, consider filling them with 'Unknown' or using another appropriate strategy.

**Replaced with Find and Replace** 

# Data Transformation:
1)	Split the ‘names’ column in the “Customer Names” Table into 3 meaningful columns: ‘Title’, ‘First Name’, and ‘Last Name’.

**Names were split using Text to Columns**

2)	Convert the "Number Of Major Surgeries" column in the “Medical Examinations” Table to numerical data by replacing non-numeric characters with meaningful numerical values.
   
**Replaced with Find and Replace**

4)	Check for inconsistencies in the 'Heart Issues' and 'smoker' columns and propose corrective actions if necessary.

Inconsistencies were corrected using the PROPER function 

Syntax **=PROPER(Table1[@Smoker3])**

5)	Create a new column named “Weight Status” that categorizes BMI into different categories as below:
 
 BMI was categorized into different weight statuses using the IF function.

Syntax **=IF(Table1[@BMI]<18.5,"Under Weight",IF(Table1[@BMI]<24.9,"Normal Weight",IF(Table1[@BMI]<29.9,"Overweight","Obesity")))**

7)	Create a new column named “Diabetes Status” and fill it as per the information given below:
 
 HBA1C was categorized into different diabetic statuses using “IF” function 
 
 Syntax **=IF(Table1[@HBA1C]<5.7,"Normal",IF(Table1[@HBA1C]<6.4,"Prediabetes","Diabetes"))**


8)	Merge ‘year’, ‘month’ and ‘date’ columns in the “Hospitalization Details” Table into one column named ‘Date of Birth’ and format it in ‘DD-MMM-YYYY’ custom format.
   
**Merged by using CONCATENATE function**

Syntax **=CONCATENATE([@date],"-",[@Month2],"-",[@Year2])** 

10)	Calculate the ‘Age’ of each customer based on their ‘Date of Birth’ and the date of collection of the dataset, which is 8thJune 2023.

Age was calculated using the DATEDIF function. 

Syntax ** =DATEDIF([@[Date of Birth]],DATE(2023,6,8),"Y")**

11)	Format ‘charges’ column as currency ($).

**Charges column format changed  to currency**

# Data Exploration, Analysis & Visualization: 
➢	Create a new sheet named “Healthcare", combine all three tables into one, using Customer ID as the common column, utilizing VLOOKUP.
➢	Retain the following necessary columns: Customer ID, First Name, BMI, HBA1C, Heart Issues, Any Transplants, Cancer history, NumberOfMajorSurgeries, smoker, Weight Status, Diabetes Status, Date of Birth, charges, Hospital tier, City tier, State ID, Age.

Combined tables by using VLOOKUP function

Syntax **=VLOOKUP(Table1[[#Headers],[HBA1C]],Table1[[#All],[HBA1C]],1,FALSE)**

# Analysis using Pie/Donut Chart:

➢	What is the distribution of cancer history among smokers and non-smokers?

**Values were obtained using a PivotTable and Pie chart added**

➢	How does the total number of major surgeries and average HbA1C differ between patients with and without a history of transplants?

**Values were obtained using a PivotTable and Pie chart added**

# Analysis using Column/Bar Chart:

➢	How do healthcare charges vary based on different weight statuses and diabetes statuses?

**Values were obtained using a PivotTable and Bar chart added**

➢	Can you compare the average charges for each hospital tier within different states?

**Values were obtained using a PivotTable and Column chart added**

# Analysis using Line/Scatter Plot:

➢	Is there any correlation between age and both BMI and HbA1C in the dataset?

**Values were obtained using a PivotTable and Line chart added**

➢	Explore the relationship between age and healthcare charges.
**Values were obtained using a PivotTable**

# Dashboard Creation:
➢	Build an interactive dashboard that consolidates all key insights using the above visualizations. Ensure visual clarity and ease of interpretation for all chart types.
➢	The dashboard was created with all charts 
➢	Add slicers for the fields “Weight Status” and “Diabetes Status” to enable filtering across all visualizations, supporting comparison of health outcomes and charges based on body weight and diabetes condition.
➢	Slicers added
➢	**Pivot chart Analyze – Insert slicer**


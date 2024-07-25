This dashboard provides an in-depth analysis of the Titanic disaster. It helps in understanding the demographics of the passengers, the survival rate based on different factors such as class, gender, age, and fare. This dashboard aims to identify patterns and insights that can help in understanding the tragedy and could provide valuable lessons for future maritime safety.

Steps Followed
Step 1: Load Data

Data was loaded into Power BI Desktop from a CSV file containing the Titanic passenger data.
Step 2: Data Cleaning and Preparation

Opened the Power Query Editor.
Checked "column distribution," "column quality," and "column profile" options in the Data preview section.
Set column profiling based on the entire dataset.
Addressed missing values and errors, particularly in columns like "Age" and "Cabin."
Step 3: Visual Design

Selected a theme for consistency in the report view.
Added various visuals to represent the data, including bar charts, pie charts, and card visuals.
Step 4: Key Metrics and Visuals

Survival Rate: Displayed the survival rate using pie charts to show the proportion of survivors and non-survivors.
Passenger Class: Used bar charts to represent the number of passengers in each class and their respective survival rates.
Gender Analysis: Segregated data by gender to show the survival rate for males and females.
Age Distribution: Created age groups and displayed the survival rate within each age group using bar charts.
Fare Analysis: Represented fare distribution and its impact on survival rates using scatter plots and box plots.
Deck Analysis: Visualized the distribution of passengers across different decks and their survival rates.
Step 5: Advanced Calculations

Calculated Columns:
Created age groups using DAX expressions to categorize passengers into different age ranges.
Measures:
Created measures to calculate the total number of passengers, survival rates, and average fare.
Detailed Steps and DAX Expressions
Creating Age Groups:

DAX
Age Group = 
if(Titanic[Age]<=12, "0-12 (Children)",
if(Titanic[Age]<=18, "13-18 (Teenagers)",
if(Titanic[Age]<=35, "19-35 (Young Adults)",
if(Titanic[Age]<=60, "36-60 (Adults)",
"60+ (Seniors)")))

Calculating Total Passengers:
Total Passengers = COUNT(Titanic[PassengerId])

Calculating Survival Rate:
dax
Survival Rate = DIVIDE(CALCULATE(COUNT(Titanic[PassengerId]), Titanic[Survived] = 1), [Total Passengers])
Publishing
Published the report to Power BI Service for broader access and collaboration.
Insights
The dashboard provides the following insights:

Total Number of Passengers: 2,224
Survival Rate:

Total survivors: 710 (32%)
Total non-survivors: 1,514 (68%)
Passenger Class:

First Class: 325 passengers, 63% survived.
Second Class: 285 passengers, 47% survived.
Third Class: 709 passengers, 24% survived.
Gender Analysis:

Males: 1,348 passengers, 20% survived.
Females: 876 passengers, 75% survived.
Age Distribution:

Children (0-12): 109 passengers, 50% survived.
Teenagers (13-18): 72 passengers, 42% survived.
Young Adults (19-35): 597 passengers, 40% survived.
Adults (36-60): 494 passengers, 37% survived.
Seniors (60+): 22 passengers, 33% survived.
Fare Analysis:

Higher fare categories generally had higher survival rates.
Average fare for survivors: $50
Average fare for non-survivors: $20
Deck Analysis:

Passengers on higher decks had higher survival rates.

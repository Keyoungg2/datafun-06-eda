# Specification for Project 6 EDA Notebook

- Project objective:Create EDA Notebook
- GitHub Repository: datafun-06-eda
- Documentation: README.md
- Notebook: young_proj6_edanotebook.ipynb

## Overview

Project 6 is an opportunity to create your own custom
exploratory data analysis (EDA) project using
GitHub, Git, Jupyter, pandas, Seaborn and other popular data analytics tools.

## Dataset 

I used a loan application site database that pulled loan application information. 
Data source: https://github.com/mwaskom/seaborn-data/blob/master/healthexp.csv

Data set example
|Year  |Country|Spending_USD|Life_Expectancy|
|------|-------|----------|----------|
|1970  |Germany|252.311|70.6|	


## External Dependencies

This project will likely use at least the following external modules, so a virtual environment is recommmended.
You may adjust packages used as needed.

- jupyterlab
- pandas
- pyarrow
- matplotlib
- seaborn

## Version Control with Git

- Create a new GitHub repository named `datafun-06-eda`.
- Clone the repository to your local machine.
- Document the steps and commands in your README.md.
- Document your workflow and commands as you edit, add, commit, and push changes to the GitHub repository.

## Objective

Perform and publish a custom EDA project to demnostrate skills with Jupyter, pandas, Seaborn and popular tools for data analytics.
The notebook should tell a data story and visually present findings
in a clear and engaging manner.

## Requirements 

### 1. Environment Setup

1. **Create** and **activate** the project virtual environment.
1. Install all required packages into your local project virtual environment.
1. After installing the required dependencies, update or generate a  **requirements.txt** file.
1. Add a **.gitignore** file to your project with useful entries. See [.gitignore](.gitignore) example.
1. Document the steps and commands in your README.md.

### 2. Project Start

Make sure Jupyter is installed and working in your project virtual environment.
Document the process and commands you used in your README.md.

Then create, open, and start a new notebook in your root project repository folder:

1. Create the Notebook: In the VS Code Explorer, create a new file i.e., yourname_eda.ipynb. Ensure it has a .ipynb extension.
print(df.head(10))
print(df.shape)
print(df.dtypes)
```
#### Step 3. Initial Descriptive Statistics

Use the DataFrame describe() method to display summary statistics for each column.

Jupyter Notebook / Python cell example:

```python
print(df.describe())
```

#### Step 4. Initial Data Distribution for Numerical Columns

Choose a numerical column and use df['column_name'].hist() to plot a histogram for that specific column.
To show all the histograms for all numerical columns, use df.hist().

Jupyter Notebook / Python cell example:

```python
# Inspect histogram by numerical column
df['sepal_length'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()
```
Afterwards, use a Markdown cell to document your observations.

#### Step 5. Initial Data Distribution for Categorical Columns

Choose a categorical column and use df['column_name'].value_counts() to display the count of each category.
Use a loop to show the value counts for **all** categorical columns.

Jupyter Notebook / Python cell example:

```python
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()
```

Afterwards, use a Markdown cell to document your observations.

#### Step 6. Initial Data Transformation and Feature Engineering

Use pandas and other tools to perform transformations.
Transformation may include renaming columns, adding new columns,
or transforming existing data for more in-depth analysis.

For this project, you must:

1. Rename at least one column.
2. Add at least one column.

#### Step 7. Initial Visualizations

Create a variety of chart types using seaborn and matplotlib to showcase different aspects of your data.
For each chart, include the goal - what you want to learn/explore, the type of chart you choose, display the chart, and tell your data story. Use Markdown cells and Python cells. Create at least 3 subsections - each subsection should have the following parts:

1. Goal: The question you are exploring.
2. Chart Type: Tell us what kind of chart you choose to illustrate this goal.
3. Chart: Display the chart.
4. Story: Use Markdown cell(s) to document your observations and insights.

#### Step 8. Initial Storytelling and Presentation

Present your notebook with an opening that introduces yourself and your topic.
Use Markdown section headings to introduce each step.
Interpret the visualizations and statistics to narrate a clear and compelling data story.
Present your findings in a logical and engaging manner.


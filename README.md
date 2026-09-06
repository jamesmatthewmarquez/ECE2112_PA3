# ECE2112_PA3
### Intended Learning Outcome
1. Load a CSV dataset into a Pandas DataFrame
2. Select rows and columns using positional and label-based indexing
3. Filter records using conditions on a DataFrame column
4. Extract a well-defined subset of data without changing the source data
---
### Instructions
Use the same `cars.csv` dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook and import Pandas as pd. The dataset contains the Model column together with the vehicle variables used in the original experiment

• Load the CSV file into a DataFrame named cars

• Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any requested table or answer

• Do not modify values in cars; create a new DataFrame or Series for each requested subset

• Preserve the row order of the source dataset unless stated otherwise

• Display every requested result in an executed notebook cell

---
## A. POSITIONAL AND LABEL-BASE SLICING
Display the shape and complete list of column names of cars. Using positional slicing, `create cars_6_to_10` containing rows 6 through 10 of the dataset, where the first data row is row 1. From `cars_6_to_10`, display only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that order

<table>
  <tr>
    
    import pandas as pd
    
    cars = pd.read_csv('cars.csv')
    cars
    
    cars.shape
    
    cars.columns
    
    cars_6_to_10 = cars.iloc[5:10]
    cars_6_to_10
    
    cars_6_to_10 [['Model', 'mpg', 'cyl', 'hp', 'gear']]
    
  </tr>
</table>

- `import pandas as pd` - Loads the Pandas library into Python using the standard `pd` shortcut, allowing you to use all of its data manipulation functions

- `cars = pd.read_cvs('cars.cvs')` - Uses `pd.read_csv()` to import the external .cvs file named `cars.csv` and store its data inside a 2D tabular structure called a DataFrame assigned to the variable `cars`

- `cars.shape` - Retrieves the basic dimensions of the DataFrame returning a tuple showing `(number of rows, number of columns)`

- `cars.column` - Displays the names of all the column headers present in the cars DataFrame

- `cars_6_to_10 = cars.iloc[5:10]` - Uses integer-positional slicing `.iloc` to extract rows from index position 5 up to index 10 but does not include index 10 in the print. This pulls rows 6 through 10 and saves them to a new DataFrame variable called `cars_6_to_10`

- `cars_6_to_10 [['Model', 'mpg', 'cyl', 'hp', 'gear']]` - Selects a subset of specific columns `('Model', 'mpg', 'cyl', 'hp', and 'gear')` from `cars_6_to_10` and prints only those 5 columns

---
## B. MODEL LOOKUP
Display the complete row for "Toyota Corolla". For "Pontiac Firebird", display only `Model`, `mpg`, `hp`, and `wt`. Store the two results in "toyota" and "pontiac", respectively

<table>
  <tr>
    
    import pandas as pd
    
    cars = pd.read_csv('cars.csv')
    cars

    cars.iloc[[19]]

    toyota = cars.iloc[[19]]
    toyota

    cars.loc[[24], ['Model', 'mpg', 'hp', 'wt']]

    pontiac = cars.loc[[24], ['Model', 'mpg', 'hp', 'wt']]
    pontiac
    
  </tr>
</table>

- `cars.iloc[[19]]` - Uses positional indexing `.iloc` with double brackets to retrieve the row at index position 19 (the 20th row of the dataset) and keep it formatted as a 1 row DataFrame

- `toyota = cars.iloc[[19]]` - Selects that same row at index 19 and assigns it to a new variable called `toyota`

- `cars.loc[[24], ['Model', 'mpg', 'hp', 'wt']]` - Uses label indexing `.loc` to select the row with index label 24 while filtering for only the `Model`, `mpg`, `hp`, and `wt` columns

- `pontiac = cars.loc[[24], ['Model', 'mpg', 'hp', 'wt']]` - Takes that selected row and specific columns for index 24 and stores it in a new variable called `pontiac`

---
## C. MULIT-MODEL SUBSETTING
Create a DataFrame named selected cars containing only the records for three models: "Datsun 710", "Lotus Europa", and "Ferrari Dino". For these records, retain only `Model`, `mpg`, `cyl`, `hp`, and `gear`. Select the rows by their model values rather than by row numbers. Display selected cars and its shape

<table>
  <tr>
    
    import pandas as pd
    
    cars = pd.read_csv ('cars.csv')
    cars

    selected_cars = cars[(cars['Model'] == 'Datsun 710')|
                         (cars['Model'] == 'Lotus Europa')|
                         (cars['Model'] == 'Ferrari Dino')] [['Model', 'mpg', 'cyl', 'hp', 'gear']]
    selected_cars

    selected_cars.shape
    
  </tr>
</table>

- `selected_cars = cars[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino')] [['Model', 'mpg', 'cyl', 'hp', 'gear']]` - Uses boolean indexing with the `|` (OR) operator to search the `Model` column and filter for rows matching "Datsun 710", "Lotus Europa", or "Ferrari Dino". It also selects only the 5 specified columns (`Model`, `mpg`, `cyl`, `hp`, and `gear`) from those filtered rows and saves this 3-row, 5-column result into a new variable called `selected_cars`

- `selected_cars.shape` - Returns the tuple (3, 5), which verifies that your filtered DataFrame contains exactly 3 rows and 5 columns

To view the main python program for Programming Assignment 3, click this link
https://github.com/jamesmatthewmarquez/ECE2112_PA3/blob/main/ECE2112_PA3.ipynb and download. Open in Jupyter Notebook, then run all cells.

**README file Version History:**

September 7, 2026

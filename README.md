# ECE2112-PA3
## Experiment 3: Python Data Analysis (Pandas)

#### Setup & Loading
Initialize Pandas and load the dataset.
```python
import pandas as pd

# Load the CSV file into a DataFrame named cars
cars = pd.read_csv('cars.csv')
```

#### A. Positional and Label-Based Slicing
**Tasks:** 
- Display the shape and complete list of column names of cars.
- Using positional slicing, create cars6_to_10 containing rows 6 through 10 of the dataset, where the first data row is row 1.
- Display specific columns (`Model`, `mpg`, `cyl`, `hp`, `gear`) using label-based indexing.

**Code:**
```python
# a. Print the shape and complete list of column names
print("Shape of cars:", cars.shape)
print("Column names:", cars.columns.tolist())

# b. Create cars_6_to_10 using positional slicing (iloc)
cars_6_to_10 = cars.iloc[5:10]

# c. Display only the requested columns in exact order using label-based indexing
cars_6_to_10.subset[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
cars_6_to_10.subset
```

#### B. Model Lookup
**Tasks:**
- Using Boolean indexing on the Model column:
- Display the complete row for `Toyota Corolla`.
- Display only (`Model`, `mpg`, `hp`, `wt`) for `Pontiac Firebird`.

**Code:**
```python
# a. Display the complete row for Toyota Corolla
toyota = cars[cars['Model'] == 'Toyota Corolla']
display(toyota)

# b. Model, mpg, hp, and wt of Pontiac Firebird
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```

#### C. Multi-Model Subsetting
**Tasks:**
- Create a DataFrame named selected cars containing only the records for three models: Datsun 710, Lotus Europa, and Ferrari Dino.
- For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values rather than by row numbers. Display selected cars and its shape.
- The final DataFrame must contain exactly three rows and five columns.

**Code:**
```python
# Create the subset retaining only the specified models and columns
selected_cars = cars.loc[cars['Model'].isin(target_models), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
# Define the requested models
target_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']

# Display selected_cars and its shape
display(selected_cars)
print("Shape of selected_cars:", selected_cars.shape) 
```

---

# Data-Scientist-Associate-Certification - DS501P
**RealAgents** is a real estate company that focuses on selling houses.  
RealAgents sells a variety of types of houses in one metropolitan area.  
Some houses sell slowly and sometimes require lowering the price in order to find a buyer.  
In order to stay competitive, RealAgents would like to optimize the listing prices of the houses it is trying to sell.  
They want to do this by predicting the sale price of a house given its characteristics.  
If they can predict the sale price in advance, they can decrease the time to sale.

---

### Data
The dataset contains records of previous houses sold in the area.

| Column Name      | Criteria                                                                                                                                  |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **house_id**      | Nominal. Unique identifier for houses. Missing values not possible.                                                                        |
| **city**          | Nominal. The city in which the house is located. One of 'Silvertown', 'Riverford', 'Teasdale' and 'Poppleton'. Replace missing values with "Unknown". |
| **sale_price**    | Discrete. The sale price of the house in whole dollars. Values can be any positive number greater than or equal to zero. Remove missing entries. |
| **sale_date**     | Discrete. The date of the last sale of the house. Replace missing values with 2023-01-01.                                                  |
| **months_listed** | Continuous. The number of months the house was listed on the market prior to its last sale, rounded to one decimal place. Replace missing values with mean number of months listed, to one decimal place. |
| **bedrooms**      | Discrete. The number of bedrooms in the house. Any positive values greater than or equal to zero. Replace missing values with the mean number of bedrooms, rounded to the nearest integer. |
| **house_type**    | Ordinal. One of "Terraced" (two shared walls), "Semi-detached" (one shared wall), or "Detached" (no shared walls). Replace missing values with the most common house type. |
| **area**          | Continuous. The area of the house in square meters, rounded to one decimal place. Replace missing values with the mean, to one decimal place. |

### Task 1  
The team at RealAgents knows that the city that a property is located in makes a difference to the sale price.  
Unfortunately, they believe that this isn't always recorded in the data.

**Instructions:**
- Calculate the number of missing values in the 'city' column.
- You should use the data in the file "house_sales.csv".
- Your output should be an object named `missing_city`, which contains the number of missing values in this column.

- ### Task 2  
Before you fit any models, you will need to make sure the data is clean.

The table below shows what the data should look like. Create a cleaned version of the dataframe.

**Instructions:**
- You should start with the data in the file "house_sales.csv".
- Your output should be a dataframe named `clean_data`.
- All column names and values should match the criteria described below:

| **Column Name**  | **Criteria** |
| ---------------- | ------------ |
| **house_id**      | Nominal. Unique identifier for houses. Missing values not possible. |
| **city**          | Nominal. The city in which the house is located. One of 'Silvertown', 'Riverford', 'Teasdale' and 'Poppleton'. Replace missing values with "Unknown". |
| **sale_price**    | Discrete. The sale price of the house in whole dollars. Values can be any positive number greater than or equal to zero. Remove missing entries. |
| **sale_date**     | Discrete. The date of the last sale of the house. Replace missing values with 2023-01-01. |
| **months_listed** | Continuous. The number of months the house was listed on the market prior to its last sale, rounded to one decimal place. Replace missing values with the mean number of months listed, to one decimal place. |
| **bedrooms**      | Discrete. The number of bedrooms in the house. Any positive values greater than or equal to zero. Replace missing values with the mean number of bedrooms, rounded to the nearest integer. |
| **house_type**    | Ordinal. One of "Terraced", "Semi-detached", or "Detached". Replace missing values with the most common house type. |
| **area**          | Continuous. The area of the house in square meters, rounded to one decimal place. Replace missing values with the mean, to one decimal place. |

### Task 3

The team at RealAgents believes that the number of bedrooms is the biggest driver of house price.

Your task is to produce a table showing the average sale price and variance in sale price by the number of bedrooms.

**Instructions:**
- Start with the data in the file 'house_sales.csv'.
- Your output should be a dataframe named `price_by_rooms`.
- The dataframe should include the following three columns:
  - `bedrooms`: The number of bedrooms.
  - `avg_price`: The average sale price for houses with that number of bedrooms.
  - `var_price`: The variance in sale price for houses with that number of bedrooms.
- Round your answers to **1 decimal place**.

- ### Task 4

Your task is to fit a **baseline model** to predict the sale price of a house.

**Steps:**
1. **Train the model** using the data in **`train.csv`**.
2. **Predict the sale price** of houses using the **`validation.csv`** data.
3. Return a dataframe named **`base_result`** which should contain the following columns:
   - `house_id`: The unique identifier for each house.
   - `price`: The predicted sale price.

### Requirements:
- The `price` column should contain the predicted values based on the model you fitted.

- ### Task 5

In this task, your objective is to fit a **comparison model** to predict the sale price of a house.

**Steps:**
1. **Train the comparison model** using the data in **`train.csv`**.
2. **Predict the sale price** of houses using the data from **`validation.csv`**.
3. Return a dataframe named **`compare_result`** which should contain the following columns:
   - `house_id`: The unique identifier for each house.
   - `price`: The predicted sale price from the comparison model.

### Requirements:
- The `price` column should include the predicted values from your newly fitted model for comparison purposes.

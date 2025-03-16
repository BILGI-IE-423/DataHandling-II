# 📊 Data Wrangling with Pandas  

Now that we have explored the basics of Pandas, let's move on to more advanced tasks related to **data manipulation**, focusing on **handling date/time data efficiently**.

---

## 🕒 **Exercise 1: Working with Date/Time Data in Pandas**

### **Task 1: Creating Date/Time Objects**
- Import the necessary libraries: `pandas` and `datetime`.
- Create a **datetime object** for today’s date and display it.
- Convert the following strings into **datetime format** using Pandas:  
  - `'2023-10-15'`  
  - `'15-10-2023'`  
  - `'October 15, 2023'`  
- Extract the **year, month, and day** from the converted datetime objects.

### **Task 2: Performing Date Calculations**
- Calculate the **number of days** between:
  - Today and **January 1, 2000**.
  - Your birthday and today's date.
- Create a **new column** in a dataset where:
  - The column contains random dates between **2010-01-01 and 2023-01-01**.
  - Extract the **day of the week** for each date.

### **Task 3: Handling Time Series Data**
- Import the dataset **timeseries.csv**.
- Convert the column `date` to a **datetime object**.
- Set the **date column as an index**.
- Resample the data to show the **monthly average**.
- Extract the subset of data from **2019 to 2021** and display it.

---

# 🌊 Data Wrangling with Pandas: Vessel Transit Data  

In this exercise, we will manipulate data collected from ocean-going vessels using **Automatic Identification System (AIS)** transponders. The dataset includes transit segment information such as **start and end times, vessel speed, and distance traveled**. 

Our goal is to clean, transform, and analyze this data efficiently using Pandas.

---

## 🚢 **Exercise 2: Handling and Analyzing Vessel Transit Data**

### **Task 1: Importing and Exploring the Data**
- Import the dataset **transit_segments.csv** using Pandas.
- Display the first **5 rows** of the dataset.
- Check the **data types** of all columns.
- Identify if there are any **missing values** in the dataset.

---

### **Task 2: Converting Date/Time Columns**
- Convert the columns **st_time** and **end_time** to a `datetime` format.
- Verify that the conversion was successful by checking the **data types**.
- Extract and display the **year, month, and day** from the `st_time` column.
- Extract the **hour** from `st_time` and create a new column named **start_hour**.
- Filter the dataset to show only records where the month is **February**.

---

### **Task 3: Calculating Transit Duration**
- Create a new column **transit_duration** that calculates the **difference** between `end_time` and `st_time`.
- Convert `transit_duration` to **hours** and display the first 10 rows.
- Find the **longest** and **shortest** transit durations.

---

### **Task 4: Analyzing Vessel Speed and Distance**
- Compute and display the **average segment length (`seg_length`)**.
- Compute and display the **average speed (`avg_speed`)**.
- Identify the **fastest** and **slowest** recorded vessel speeds.
- Create a **histogram** of `seg_length` to visualize the distribution.
- Apply a **log transformation** to `seg_length` and plot the histogram again.

---

### **Task 5: Filtering and Grouping Data**
- Find all transit records where:
  - The vessel speed is greater than **20 knots**.
  - The segment length is greater than **50 km**.
- Group the data by **month** and compute the **average segment length per month**.
- Identify the **month with the highest average transit duration**.

---

### **Task 6: Resampling and Aggregation**
- Set `st_time` as the **index** of the dataset.
- Resample the data by **week** and compute the **total number of transits per week**.
- Resample by **month** and compute the **average speed per month**.

---

# 🔗 Data Wrangling with Pandas: Merging and Joining DataFrames  

Now that we have the vessel transit information, we want to enhance our dataset by adding details about the vessels themselves. The dataset **vessel_information.csv** contains additional information about each vessel, which we will merge with our **transit_segments.csv** dataset.

The challenge is that multiple vessels have traveled through multiple segments, resulting in a **one-to-many relationship** between these datasets. We will use Pandas' merging and joining capabilities to combine these datasets effectively.

---

## 🚢 **Exercise 3: Merging and Joining DataFrames in Pandas**

### **Task 1: Importing and Exploring the Datasets**
- Import the dataset **transit_segments.csv** and store it as `segments`.
- Import the dataset **vessel_information.csv** and store it as `vessels`, setting the column **mmsi** as the index.
- Display the first **5 rows** of both datasets.
- Check for missing values in both datasets.

---

### **Task 2: Merging DataFrames using Common Keys**
- Merge `segments` and `vessels` using the **mmsi** column.
- Ensure that all vessel information is correctly assigned to its respective segment.
- Display the first **5 rows** of the merged dataset.

---

### **Task 3: Exploring Different Types of Joins**
- Perform the following types of joins and explain the differences:
  - **Inner Join** (default) – Include only matching records.
  - **Outer Join** – Include all records, filling missing values where necessary.
  - **Left Join** – Include all records from `segments`, and only matching records from `vessels`.
  - **Right Join** – Include all records from `vessels`, and only matching records from `segments`.

---

### **Task 4: Handling Conflicting Column Names**
- Add a new column named **type** to `segments` and set it to `'Transit'`.
- Perform a merge with `vessels` and observe how Pandas handles duplicate column names.
- Rename conflicting column names by specifying **custom suffixes**.

---

### **Task 5: Verifying and Cleaning the Merged Data**
- Check for and handle any missing values in the merged dataset.
- Drop any unnecessary or duplicate columns after merging.
- Reset the index of the merged DataFrame if needed.

---

# 🔗 Data Wrangling with Pandas: Merging and Concatenating DataFrames  

In this exercise, we will explore **fixing merge operations** and **concatenating DataFrames** efficiently. We will work with vessel transit data and microbiome datasets to understand how to merge, append, and combine data.

---

## 🚢 **Exercise 4: Fixing Merges and Concatenating DataFrames**

### **Task 1: Fixing an Incorrect Merge**
- Import the datasets **transit_segments.csv** and **vessel_information.csv**.
- Attempt to merge the datasets and observe if the result is empty.
- Identify the reason why the merge does not return any results.
- Apply the correct merging method to ensure that vessel information is correctly assigned to the transit segments.
- Verify that the merged DataFrame contains valid records.

---

## 🦠 **Task 2: Importing and Exploring Microbiome Data**
- Import the microbiome datasets **microbiome_MID1.xls** and **microbiome_MID2.xls**.
- Read the datasets while ensuring that the first column is used as the index.
- Standardize the column names to maintain consistency across both datasets.
- Display the shape and structure of both datasets.
- Check for missing values and assess the uniqueness of the index.

---

## 🔄 **Task 3: Concatenating Data Vertically (Appending Rows)**
- Concatenate the two microbiome datasets by stacking their rows.
- Verify the shape of the resulting DataFrame.
- Check if there are any duplicate index values after concatenation.
- If duplicates exist, determine how they should be handled.

---

## 📊 **Task 4: Concatenating Data Horizontally (Merging Columns)**
- Concatenate the two microbiome datasets by aligning them column-wise.
- Verify the shape of the concatenated DataFrame.
- Ensure that indices are correctly matched and aligned after concatenation.

---

## 🔍 **Task 5: Handling Duplicates After Concatenation**
- Identify any duplicate indices in the concatenated dataset.
- Implement a method to handle duplicate index values appropriately.
- If necessary, aggregate duplicate entries by summing their values.

---

# 🔄 Data Wrangling with Pandas: Reshaping DataFrames  

In this exercise, we will explore different ways to **reshape** a dataset using Pandas. We will focus on **stacking, pivoting, melting, and creating pivot tables** to transform a dataset into different formats suitable for analysis.

We will work with **cdystonia.csv**, a dataset from a randomized controlled trial on botulinum toxin type B (BotB) in patients with cervical dystonia. The dataset contains repeated measurements for each patient, making it suitable for **longitudinal data analysis**.

---

## 🏥 **Exercise 5: Reshaping DataFrames in Pandas**

### **Task 1: Importing and Exploring the Dataset**
- Import the dataset **cdystonia.csv**.
- Display the first few rows of the dataset.
- Check the data types and structure of the dataset.
- Identify which columns contain repeated measurements for each patient.

---

## 🔀 **Task 2: Stacking and Unstacking Data**
- Convert the dataset into a **stacked format** where multiple columns are converted into rows.
- Verify the structure of the stacked DataFrame.
- Convert the stacked data **back to its original format** using an unstacking method.

---

## 📊 **Task 3: Pivoting Data**
- Transform the dataset from **long format to wide format** using a pivoting method.
- Set the patient identifier as the **index** and measurement weeks as **columns**.
- Ensure that the values of the response variable (`twstrs`) are correctly placed in the table.

---

## 🔄 **Task 4: Converting from Wide to Long Format**
- Convert the **wide format back to long format** using a melting method.
- Specify identifier columns that should remain unchanged.
- Ensure that the melted DataFrame contains **two columns**: one for the time variable and one for the measurement values.

---

## 📌 **Task 5: Creating Pivot Tables**
- Create a **pivot table** that summarizes the maximum TWSTRS score per treatment group and site.
- Display the **hierarchical index** structure of the pivot table.
- Analyze the differences in TWSTRS scores across sites and treatments.

---

## 🔢 **Task 6: Performing Cross-tabulation**
- Generate a **cross-tabulation table** to count the number of male and female participants at each study site.
- Interpret the distribution of participants across different study locations.

---

# 🔄 Data Wrangling with Pandas: Data Transformation  

In this exercise, we will explore various **data transformation techniques** in Pandas, including **handling duplicates, replacing values, and creating indicator variables**. These transformations help in **cleaning, structuring, and preparing** data for analysis.

We will apply these techniques to datasets such as **vessels.csv** (containing vessel information) and **cdystonia.csv** (a dataset from a clinical trial on cervical dystonia).

---

## ⚙ **Exercise 6: Data Transformation in Pandas**

### **Task 1: Identifying and Removing Duplicates**
- Import the **vessels.csv** dataset.
- Identify duplicate records based on the vessel names.
- Remove duplicate vessel names while keeping only the first occurrence.
- Verify that the duplicates have been removed.

---

## 🔢 **Task 2: Replacing Categorical Values with Numeric Codes**
- Import the **cdystonia.csv** dataset.
- Identify categorical columns that should be converted into numerical values.
- Replace treatment group names with numeric values:
  - Assign `0` for Placebo.
  - Assign `1` for 5000U.
  - Assign `2` for 10000U.
- Verify the transformation by checking the first few rows of the modified column.

---

## 🔄 **Task 3: Replacing Numeric Values with Categorical Labels**
- Convert the numeric treatment values back into categorical labels.
- Ensure that the transformation correctly restores the original treatment names.

---

## 📊 **Task 4: Creating Indicator Variables (Dummy Variables)**
- Identify a categorical column in **vessels.csv** that would be useful as indicator variables.
- Convert this categorical column into **dummy variables**.
- Verify that the new DataFrame contains **binary indicator columns**.

---

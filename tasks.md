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




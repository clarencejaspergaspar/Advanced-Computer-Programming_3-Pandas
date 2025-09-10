# Advanced Computer Programming and Algorithms 

## Experiment 3: Pandas

Name: Clarence Jasper S. Gaspar      

Section: 2ECE-B

---

**Overview**

This repository is created to showcase various programming activities, specifically Python programming. It will serve both as a submission bin and a portfolio for Advanced Computer Programming and Algorithms. All activities are developed using Jupyter Notebook (Anaconda) and then exported and uploaded here to GitHub. Each activity demonstrates different Python concepts, functions, and problem-solving approaches in the course.
<br><br>



📌 **Tools Used**

*Anaconda* – to manage Python environments and launch Jupyter Notebook.

*Jupyter Notebook* – to write, run, and test Python programs interactively.

*GitHub* – to store and showcase the Python programming activities.
<br><br>



📝 **Workflow**

1. Write Code in Jupyter Notebook

    - Open Jupyter Notebook from Anaconda Navigator.

    - Create a python(.ipynb) file for each activity.

    - Use functions, loops, and other Python concepts to solve tasks.

2. Export Activity

    - Save work as .ipynb which is the default Jupyter format.

3. Upload to GitHub

    - Create a new repository in GitHub.

    - Upload the .ipynb file(s) to the repository.
  
    - Aside from .ipynb file, .csv file was also uploaded as part of the Module 3(pandas)

4. Organize Portfolio

    - Each activity will have its own repository and own section of README.
    - Tasks will be documented with short explanations and screenshots.


<br><br>

---

📂 **Activities**

The original files for these activities are uploaded in this repository alongside this README file. Each activity is written in Python and can be previewed directly on GitHub using its notebook preview feature. However, to fully run the programs and provide inputs, the files should be imported into coding platforms such as Jupyter Notebook from Anaconda. The Python codes already contain short comments denoted by # to guide readers through the logic. Furthermore, the information below provides additional explanations to further clarify how each part of the program works.

---

🔹 *Experiment 3: PYTHON DATA ANALYSIS (PANDAS)*

**I. Intended Learning Outcomes:**
<br><br> 
    1. To identify the codes and functions incorporated in the Pandas library.
<br>   
    2. To be able to apply and use the different codes and functions in creating a Python program using a Pandas library.
<br><br> 

**II. Instructions:**

Write a Python script/code in the Jupyter Notebook to do the given problems. For this programming assignmnent, download the csv file (csv file is uploaded in this repository, a scrrenshot of its content is provided below).


<img width="852" height="669" alt="Screenshot 2025-09-10 222039" src="https://github.com/user-attachments/assets/e8779b5d-7399-40d3-b15f-44473fb288b8" />

<br><br>

- **Problem 1: Display the first five and last five rows of the resulting cars**

  This part shows how to work with a CSV file using pandas. First, the file is loaded into a DataFrame called cars, which makes the data easier to view and manage since it is arranged in rows and columns. Then, the first five rows and the last five rows of the DataFrame are displayed using the .head() and .tail() functions. These commands give a quick look at the beginning and end of the dataset.
  
<img width="1003" height="699" alt="Screenshot 2025-09-10 222925" src="https://github.com/user-attachments/assets/c548fc53-74e0-4338-9972-316e09c04d48" />

### Code Explanation

```
import pandas as pd
```
This section of the code imports the Pandas library with a nickname pd to allow it to be called easier. Pandas will be used for handling tabular data (like spreadsheets), reading CSV files, and performing data analysis tasks.

```
cars = pd.read_csv("cars.csv")
```
This section reads the file cars.csv and returns a dataframe assigned to the variable cars.

```
print("First Five Rows:\n")
```
This prints the guideline for the first part of the task using the print() function.

```
print(cars.head(), "\n") 
```
This section returns a dataframe containing the first 5 rows by default using .head() function. The data is taken from the csv file that was called earlier using pd.read function. 

```
print("Last Five Rows:\n")
```
This prints the guideline for the second part of the task using the print() function.

```
print(cars.tail())
```
This section returns a dataframe containing the last 5 rows by default using .tail() function. The data is taken from the csv file that was called earlier using pd.read function. 



<br><br>


- **Problem 2:**

This part focuses on extracting specific information from the cars DataFrame using subsetting, slicing, and indexing. First, the task is to display the first five rows but only keep the odd-numbered columns, showing how slicing can be used to select certain parts of the table. Next, the row for the car model “Mazda RX4” is displayed to practice filtering based on a condition. The exercise also includes checking how many cylinders the “Camaro Z28” has, which demonstrates how to access a specific value from a column. Finally, it asks for both the number of cylinders and the gear type for three specific car models: “Mazda RX4 Wag,” “Ford Pantera L,” and “Honda Civic.”.

<img width="998" height="741" alt="Screenshot 2025-09-10 230323" src="https://github.com/user-attachments/assets/9130b974-87a0-4257-898f-032548ee5ad4" />




### Code Explanation

```
import pandas as pd
```
This section of the code imports the Pandas library with a nickname pd to allow it to be called easier. Pandas will be used for handling tabular data (like spreadsheets), reading CSV files, and performing data analysis tasks.

```
cars = pd.read_csv("cars.csv")
```
This section reads the file cars.csv and returns a dataframe assigned to the variable cars.

```
print("A. The first five rows with odd-numbered columns of cars:\n")
```
This prints the guideline for the first part (A) of the task using the print() function.

```
print(cars.iloc[:5, ::2], "\n\n")
```
This section obtains data from the csv file. Then slices it to display only the first five rows with odd-numbered columns of cars using .iloc function. :5 means start from the beginning (0) up to row (4). : means take all the columns, :2 means use interval of 2 in order to have an odd-ordered columns.

```
print("B. The row that contains the ‘Model’ of ‘Mazda RX4’:\n")
```
This prints the guideline for the first part (B) of the task using the print() function.

```
print(cars[cars["Model"] == "Mazda RX4"], "\n\n")
``` 

This part filters the data to look for model that matches with "Mazda RX4" in the csv file, it then displays the output using print() function. 

```
print("C. The number of cylinders of ‘Camaro Z28':", cars.loc[cars["Model"] == "Camaro Z28", "cyl"].values[0], "\n\n") 
```
This line finds the row with the model “Camaro Z28” and directly extracts the value in the “cyl” column. The result is then printed.


```
print("D. Cylinders and gear type of the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic’\n\n") 
```
This prints the guideline for the first part (D) of the task using the print() function.


```
print(cars.loc[cars["Model"].isin(["Mazda RX4 Wag", "Ford Pantera L", "Honda Civic"]), ["Model", "cyl", "gear"]]) 
```
This part selects the three specific models and only displays their Model, cyl, and gear columns.

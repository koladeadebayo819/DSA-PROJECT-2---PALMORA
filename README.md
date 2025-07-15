# INTRODUCTION
Palmoria Group is a manufacturing company based in Nigeria that has an embroided issues about gender inequality in its 3 regions where there businesses are located. Unfortunately, the media recently published in the news with the headline “Palmoria, the Manufacturing Patriarchy” this doesn’t look good to the owner of the business on their ambition to scale the business to other regions and even overseas. Disclaimer: All datasets and reports do not represent any company, institution or country, but just a dummy datasets to demonstrate capabilities of Power BI

This documentation outlines the data cleaning process for the Palmoria group Business A 3 sets of data was given to work on and to know about the issues the company is currently facing. The datasets are given below;

**The bonus mapping** : This contains the rule for making payments to the employees in the company and their work rating

**The bonus rules** : this contains the rule for making payments to the employees in the company and their work rating

**Palmoria Group emp-data** : this contains the employees details I looked into the data set and the data cleaning process was completed using Power Query, a powerful data transformation tool and I analyzed and generate an insights the management team need to address

## Problem Statement
 1. What is the gender distribution in the organization? Distil to regions and departments
 2. Show insights on ratings based on gender
 3. Analyse the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management
 4. A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000
  - Does Palmoria meet this requirement?
  - Show pay distribution of employees grouped by a band of $10,000.
  - allocate the annual bonus pay to employees based on the performance rating.
  - calculate the amount to be paid as bonus to individual employees
  - Calculate the total amount to be paid to individual employees (salary inclusive of bonus)
  - Total amount to be paid out per region and company-wide

## DATA Description;
The Palmoria Group manufacturing company gave out a data set of 3 different tables which are the bonus mapping, bonus rules and the Palmoria Group emp-data. The bonus mapping and bonus rules consists of 12 rows and 6 columns while the Palmoria Group emp-data consists of 6 columns and 1015 rows.. The Palmoria Group emp-data tables contains a range of the employees details related to the Palmoria company staffs, such as Employees name, Gender, department, salary, location and rating While the bonus rules and mappings which are the same consist of 12 rows and 6 columns .The columns consists of the department and the ratings ie very poor, poor, very good, good and average.

  - Skills/ concepts demonstrated
  - DAX
  - Qucik Measures,
  - Page Navigation
  - Modelling
  - Filters
  - Data Cleaning Process

Using M language and a host of tools available in Power Query Editor, I was able to perform the following transformation to the data set

**Text Cleaning**
One of the issues identified during the data cleaning process was with the “Gender” column. The column contains male, female and blank so I replaced the blank with Undisclosed. The power query replaced values was used. [See preview below;]

before column after column
   ![Before image](<img width="166" height="516" alt="gender1" src="https://github.com/koladeadebayo819/DSA-PROJECT-2---PALMORA/blob/main/gender1.PNG />)
   ![After image](<img width="167" height="516" alt="image" src="https://github.com/user-attachments/assets/54d68475-df77-4d44-88cd-ebb13e39f72d"/>)

**Department column**
There are few rows that has a “NULL” text in the column so I removed it by unchecking it from the list of other department rows. Which gives our rows to reduce to 987 rows [See preview below;]

before column after column
  ![Before image](<img width="168" height="511" alt="image" src="https://github.com/user-attachments/assets/829707bd-8c6d-4818-b90e-c4c7d66b952f" />)
  ![After image](<img width="164" height="451" alt="image" src="https://github.com/user-attachments/assets/47b4a544-1882-4c1a-a3c7-ccd5bbb30dae" />)


**Salary Column**
There are few rows that has a “null” text in the column so I removed it by unchecking it from the list of other salary rows. Which gives our rows to reduce to 946 rows [See preview below;]

before column after column
![before image](<img width="166" height="517" alt="image" src="https://github.com/user-attachments/assets/2fbd09d3-5fbf-4d4c-bbbc-dffd563e478d" />)
![after image](<img width="161" height="452" alt="image" src="https://github.com/user-attachments/assets/bd375bae-43a3-42e4-b8c3-f9afa015a76f" />)

Salary band column
This is a column where our condition statement was done by grouping each band into their various categories ..ie an IF statement ; For example; if [Salary] <= 60000 then “band 3” else “band 3”) . [See preview below;]

*Salary band*
![salaryband image](<img width="166" height="457" alt="image" src="https://github.com/user-attachments/assets/0e86cb58-ea47-418a-9136-12b32294db0b" />)

**Merge table**
I created a merge table to be able to get the employee who’s worthy of a bonus base on their performance rating so I was able to merge the DSF_emp_data and the bonus rules table together. I merged them by joining their unique identifier which is the “Department” column so that gives me the bonus discount column [See preview below;]

![Merged](<img width="918" height="477" alt="image" src="https://github.com/user-attachments/assets/dfbd6b27-4f4c-4bff-a3c5-ebd279590470" />)


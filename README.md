# Employee Database: A Mystery in Two Parts 

I will be conducting a research project on employees of ABC corporation from the 1980s and 1990s. All that remains in the database are six CSV files. 

I will be designing tables to hold data in the CSVs, import the CSVs into a SQL database, and answer questions about the data. 

Topics covered in this project: 
- Data Modeling
- Data Engineering
- Data Analysis

## Files
1. Department CSV: department number and department name
2. Department Employee No. CSV: emoloyee number, department number, start and end date
3. Departmnet Manager CSV: department number, employee number, start and end date 
4. Employees CSV: employee number, birth date, first name, last name, gender, hire date
5. Salaries CSV: employee number, salary, start and end date 

## Process 
Step 1: Create a table schema for each of the six CSV files. Import each CSV file into the corresponding SQL table  <br />
Step 2: Perform the following queries: <br />
- List the following details of each employee: employee number, last name, first name, gender, and salary
- List employees who were hired in 1986
- List the manager of each department with the following information: department number, department name, the manager’s employee number, last name, first name, and start and end employment dates
- List the department of each employee with the following information: employee number, last name, first name, and department name
- List all employees whose first name is “Hercules” and last names begin with “B"
- List all employees in the Sales department, including their employee number, last name, first name, and department name
- List all employees in the Sales and Development departments, including their employee number, last name, first name, and department name
- In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.

## Tools
PostgreSQL, NumPy, Pandas, Matplotlib

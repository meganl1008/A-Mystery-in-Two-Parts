# Employee Database: A Mystery in Two Parts 

I will be conducting a research project on employees of ABC corporation from the 1980s and 1990s. All that remains in the database are six CSV files. 

I will be designing tables to hold data in the CSVs, importing the CSVs into a SQL database, and answering questions about the data. 

## Files
1. Department CSV: department number and department name
2. Department Employee No. CSV: emoloyee number, department number, start and end date
3. Departmnet Manager CSV: department number, employee number, start and end date 
4. Employees CSV: employee number, birth date, first name, last name, gender, hire date
5. Salaries CSV: employee number, salary, start and end date 

## Process 
### Step 1: Data Modeling 
Inspect the CSVs and sketch out an ERD of the tables <br />
<img src = "results/erd.png" width = "50%">

### Step 2: Data Engineering
Create a table schema for each of the six CSV files and import each CSV file into the corresponding SQL table
```sql 
CREATE TABLE employees(
	emp_no INT NOT NULL,
	birth_day DATE NOT NULL,
	first_name VARCHAR(14) NOT NULL,
	last_name VARCHAR(16) NOT NULL,
	gender VARCHAR(1) NOT NULL,
	hire_date DATE NOT NULL,
	PRIMARY KEY(emp_no)
);

CREATE TABLE departments (
	dept_no VARCHAR(4) NOT NULL,
	dept_name VARCHAR(40) NOT NULL,
	PRIMARY KEY (dept_no),
	UNIQUE (dept_name)
);

CREATE TABLE dept_manager(
	dept_no VARCHAR(4) NOT NULL,
	emp_no INT NOT NULL, 
	from_date DATE NOT NULL,
	to_date DATE NOT NULL,
	FOREIGN KEY (emp_no) REFERENCES employees(emp_no),
	FOREIGN KEY (dept_no) REFERENCES departments(dept_no),
	PRIMARY KEY (emp_no, dept_no)
); 

CREATE TABLE dept_emp(
	emp_no INT NOT NULL,
	dept_no VARCHAR(4) NOT NULL,
	from_date DATE NOT NULL,
	to_date DATE NOT NULL,
	FOREIGN KEY (emp_no) REFERENCES employees(emp_no),
	FOREIGN KEY (dept_no) REFERENCES departments(dept_no),
	PRIMARY KEY (emp_no, dept_no)
); 

CREATE TABLE titles(
	emp_no INT NOT NULL,
	title VARCHAR(50) NOT NULL,
	from_date DATE NOT NULL,
	to_date DATE,
	FOREIGN KEY (emp_no) REFERENCES employees(emp_no),
	PRIMARY KEY (emp_no, title, from_date)
);

CREATE TABLE salaries (
	emp_no INT NOT NULL, 
	salary INT NOT NULL, 
	from_date DATE NOT NULL,
	to_date DATE NOT NULL,
	FOREIGN KEY(emp_no) REFERENCES employees (emp_no), 
	PRIMARY KEY(emp_no, from_date)
);
```

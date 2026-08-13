# 📊 Employee Data Practice

## 🔷 Import Libraries & Read Data

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("employee_data.txt")
```

- `pandas` = data handling
- `matplotlib.pyplot` = data visualization
- `read_csv()`= reads the dataset

## 🔷 Employee Age — Line Plot

```python
plt.plot(df["Name"], df["Age"], color="blue", marker=".", markersize=10, markerfacecolor="cyan")

plt.xlabel("Name", fontsize=10)
plt.ylabel("Age", fontsize=10)
plt.title("Age of employees", fontweight="bold", color="green", fontsize=20)
```
## OUTPUT
<img src="images/employee-age.png" alt="Employee Age Graph">

## 🔷 Employees by Department

```python
dc = df["Department"].value_counts()

plt.bar(dc.index, dc.values)

plt.xlabel("Department", fontsize=10)
plt.ylabel("No. of employees", fontsize=10)
plt.title("Employees by department", fontweight="bold", color="green", fontsize=20)
```

- `value_counts()`=counts employees in each department
- `dc.index` = department names
- `dc.values` = employee counts
- `bar()` = creates the bar chart

## OUTPUT
<img src="images/no.of-employee-by-department.png" alt="Employees by Department">

## 🔷 Average Salary by Department

```python
avg = df.groupby("Department")["Salary"].mean()

plt.bar(avg.index, avg.values)

plt.xlabel("Department")
plt.ylabel("Avg-Salary")
```

- `groupby()` → groups employees by department
- `mean()` → calculates average salary

## OUTPUT
<img src="images/avg-sal-department.png" alt="Average Salary by Department">

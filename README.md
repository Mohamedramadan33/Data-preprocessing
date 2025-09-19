# Student Dataset Cleaning and Analysis Project

This project covers the essential data science steps: data cleaning, exploratory data analysis (EDA), and machine learning, using the "Student Dataset".

---

## 1. Data Cleaning

### Initial Data Structure
* The data was first inspected using `df.info()` and `df.head()`.
* **Numerical Columns:** `Age`, `entryEXAM`, `studyHOURS`, `Python`, `DB`.
* **Categorical Columns:** `fNAME`, `lNAME`, `gender`, `country`, `residence`, `prevEducation`.

### Handling Inconsistencies
Inconsistent values were found in the following columns and were standardized:
* **`gender` column:** Found values like [Enter wrong values, e.g., 'M' or 'F'] which were standardized to [Enter correct values, e.g., 'Male' and 'Female'].
* **`country` column:** Found values like [Enter wrong values, e.g., 'Rsa' or 'usa'] which were standardized using `.str.upper()` to become [Enter correct value, e.g., 'RSA' and 'USA'].
* **`prevEducation` column:** Found typos like [Enter wrong value, e.g., 'Barrrchelors'] which were corrected to [Enter correct value, e.g., 'Bachelor'].

### Handling Duplicates
* Found [Enter number] duplicate rows.
* These duplicates were dropped using `df.drop_duplicates()`.

---

## 2. Handling Missing Data

### Identifying Missing Data
* After checking with `df.isnull().sum()`, the columns most affected by missing data were [Enter column names, e.g., 'Python' and 'DB'].

### Imputing Missing Data
The following methods were chosen to fill the missing values:
* **Numerical Columns (e.g., `Python`, `DB`):** The [Choose: Mean / or Median] was used to fill missing scores.
* **Reason:** [State the reason, e.g., "The median was chosen as it is robust to the outliers found in the scores."].
* **Categorical Columns (e.g., `country`):** The [Mode] was used to fill missing values.

---

## 3. Handling Outliers

### Detecting Outliers
* Using `sns.boxplot` and `df.describe()`, unrealistic values were detected.
* **`studyHOURS` column:** Found values [Enter values, e.g., 200 hours] which are unrealistic.
* **Score columns (`Python`, `DB`):** Found values [Enter values, e.g., negative or > 100].

### Handling Outliers
* [Choose: Rows were dropped / or The IQR method was used] to handle these values.
* **Reason:** [State the reason, e.g., "Rows with scores > 100 or < 0 were dropped as they are clear entry errors."].

---

## Final Deliverable
The cleaned data was saved to `cleaned_students.csv` after all processing steps were completed.

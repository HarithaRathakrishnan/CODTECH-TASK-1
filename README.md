Name:SR.HARITHA

Company:CODTECH IT SOLUTIONS

ID:CT4AI2697

Domain:ARTIFICIAL INTELLIGENCE

Duration:JUNE TO JULY 2024

Mentor:NEELA SANTHOSH KUMAR

OVERVIEW OF THE PROJECT

PROJECT:DATA PROCESSING

OBJECTIVES


This program is designed to interactively collect and preprocess user-provided data. It allows users to input information such as IDs, names, ages, salaries, and departments for each record. The program then cleans the data by handling missing values, applies transformations like encoding categorical variables using one-hot encoding, scales numerical features for consistency, and finally saves the processed data to a CSV file. Its goal is to streamline data preparation tasks, making them accessible and efficient for analysis or further machine learning applications.

KEY ACTIVITIES

Interactive Data Input: Facilitating user input for various data fields such as IDs, names, ages, salaries, and departments.

Data Cleaning: Handling missing values by filling them with appropriate strategies, in this case, using the mean for numerical values (ages and salaries) and filling missing departments with a default value ("Unknown").

Data Transformation: Encoding categorical variables (departments) into numerical format suitable for machine learning algorithms using one-hot encoding. This step ensures that categorical data can be used effectively in predictive models.

Feature Scaling: Standardizing numerical features (ages and salaries) to a common scale using standardization, which helps algorithms converge faster and improves model performance.

Data Output: Saving the preprocessed data into a CSV file (preprocessed_data.csv), allowing for easy retrieval and further analysis or model training.

TECHNOLOGIES USED:

Python: The core programming language used for developing the entire program.

Pandas: A powerful library for data manipulation and analysis in Python. It's used here for handling data frames, which simplifies data input, cleaning, and transformation operations.

scikit-learn (sklearn): A machine learning library in Python that provides tools for data preprocessing, modeling, and evaluation. Specifically, SimpleImputer, OneHotEncoder, StandardScaler, and other modules from sklearn.preprocessing and sklearn.compose are used for data cleaning, encoding categorical variables, and scaling features.

CSV File Handling: Standard file handling in Python is used to read from and write to CSV files (data.csv and preprocessed_data.csv). This allows for data input from the user and saving the processed data for further analysis or model training.

Interactive User Input: Python's built-in input() function is used for interactive data input, enabling users to enter data directly into the program.





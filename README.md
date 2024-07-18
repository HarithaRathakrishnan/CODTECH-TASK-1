import pandas as pd
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
def get_user_input():
    data = []
    print("Enter the data for each row. Type 'done' when finished.")
    while True:
        id_input = input("Enter ID (or type 'done' to finish): ")
        if id_input.lower() == 'done':
            break
        name = input("Enter Name: ")
        age = input("Enter Age (or leave blank if unknown): ")
        salary = input("Enter Salary (or leave blank if unknown): ")
        department = input("Enter Department (or leave blank if unknown): ")
        
        data.append([id_input, name, age if age else None, salary if salary else None, department if department else None])
    return data
    
user_data = get_user_input()
columns = ['id', 'name', 'age', 'salary', 'department']
data = pd.DataFrame(user_data, columns=columns)
data.to_csv('data.csv', index=False)
print("CSV file 'data.csv' created successfully.\n")

data = pd.read_csv('data.csv')
print("Original Data:\n", data.head())
imputer = SimpleImputer(strategy='mean')

data['age'] = imputer.fit_transform(data[['age']])
data['salary'] = imputer.fit_transform(data[['salary']])
data['department'] = data['department'].fillna('Unknown')
print("\nData after filling missing values:\n", data.head())
encoder = OneHotEncoder(sparse_output=False, handle_unknown='ignore')
encoded_departments = encoder.fit_transform(data[['department']])
encoded_department_df = pd.DataFrame(encoded_departments, columns=encoder.get_feature_names_out(['department']))
data = pd.concat([data, encoded_department_df], axis=1)
data.drop('department', axis=1, inplace=True)
print("\nData after encoding categorical variables:\n", data.head())
scaler = StandardScaler()
data[['age', 'salary']] = scaler.fit_transform(data[['age', 'salary']])
print("\nFinal Preprocessed Data:\n", data.head())

data.to_csv('preprocessed_data.csv', index=False)
print("\nPreprocessed data saved to preprocessed_data.csv")

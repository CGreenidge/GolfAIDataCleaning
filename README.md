# GolfAIDataCleaning
Overview
This script is designed to clean and preprocess CSV files containing life bear data. It handles tasks such as loading data, dropping duplicates, filling missing values, and exporting the cleaned data to new CSV files.

Dependencies
pandas: For data manipulation and analysis.
os: For file path operations.
re: For regular expression operations.
Functions
Load CSV to DataFrame
python
Copy code
def load_csv_to_dataframe(file_path):
    """Load a CSV file into a DataFrame."""
Parameters: file_path (str) - Path to the CSV file.
Returns: DataFrame or None if loading fails.
Drop Duplicates by Email
python
Copy code
def drop_duplicates_by_email(df, keep='first'):
    """Drop duplicate rows based on the 'email' column."""
Parameters:
df (DataFrame) - Input DataFrame.
keep (str) - Which duplicates to keep.
Returns: DataFrame with duplicates removed.
Change Date Format
python
Copy code
def change_date_format(df, column_name):
    """Change the date format in the specified column."""
Parameters:
df (DataFrame) - Input DataFrame.
column_name (str) - Name of the column to change.
Returns: DataFrame with updated date format.
Fill NaN Values
python
Copy code
def fill_nan_values(df, fill_value=None):
    """Fill NaN values in the DataFrame."""
Parameters:
df (DataFrame) - Input DataFrame.
fill_value (any) - Value to fill NaN entries.
Returns: DataFrame with NaN values filled.
Fill Missing Date of Birth and Gender
python
Copy code
def fill_missing_date_of_birth_and_gender(df, date_of_birth_fill='01/01/1900', gender_fill='Not Specified'):
    """Fill missing values in the 'date_of_birth' and 'gender' columns."""
Parameters:
df (DataFrame) - Input DataFrame.
date_of_birth_fill (str) - Value to fill missing DOB.
gender_fill (str) - Value to fill missing gender.
Returns: DataFrame with missing values filled.
Rename Columns
python
Copy code
def rename_columns(df, column_mapping):
    """Rename specified columns in the DataFrame."""
Parameters:
df (DataFrame) - Input DataFrame.
column_mapping (dict) - Dictionary of old and new column names.
Returns: DataFrame with renamed columns.
Validate Email
python
Copy code
def is_valid_email(email):
    """Check if the provided email is valid."""
Parameters:
email (str) - Email to validate.
Returns: bool indicating validity.
Append Invalid Emails to Garbage File
python
Copy code
def append_to_garbage_file(invalid_emails_df, garbage_file='garbage_file.csv'):
    """Append invalid email entries to the garbage file."""
Parameters:
invalid_emails_df (DataFrame) - DataFrame with invalid emails.
garbage_file (str) - File path to append invalid emails.
Filter Valid Emails
python
Copy code
def filter_valid_emails(df, email_column, garbage_file='garbage_file.csv'):
    """Filter valid emails and save invalid entries to a garbage file."""
Parameters:
df (DataFrame) - Input DataFrame.
email_column (str) - Column name containing emails.
Returns: DataFrame with valid emails.
Drop Columns
python
Copy code
def drop_columns(df, columns_to_drop):
    """Drop specified columns from the DataFrame."""
Parameters:
df (DataFrame) - Input DataFrame.
columns_to_drop (list) - List of columns to drop.
Returns: DataFrame with specified columns dropped.
Clean File
python
Copy code
def clean_file(file_path, output_file='cleaned_life_bear_data.csv'):
    """Clean a single file and export the cleaned data."""
Parameters:
file_path (str) - Path to the input CSV file.
output_file (str) - Path for the output cleaned CSV file.
Returns: Cleaned DataFrame.
Merge Cleaned Data
python
Copy code
def merge_cleaned_data(cleaned_files):
    """Merge all cleaned DataFrames into one and return it."""
Parameters:
cleaned_files (list) - List of cleaned DataFrames.
Returns: Merged DataFrame.
Main Function
python
Copy code
def main(file_paths):
    """Main workflow function to clean multiple files and merge cleaned data."""
Parameters:
file_paths (list) - List of CSV file paths to clean.
Example Usage
python
Copy code
file_paths = [
    r"/content/lifebear_dataset_chunk_1.csv",
    r"/content/lifebear_dataset_chunk_2.csv",
    r"/content/lifebear_dataset_chunk_3.csv",
    r"/content/lifebear_dataset_chunk_4.csv"
]
main(file_paths)
Conclusion
This script automates the process of cleaning and merging CSV files, making it easier to work with life bear data. Adjust the parameters as necessary for your specific dataset!

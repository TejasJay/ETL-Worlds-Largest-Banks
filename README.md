# ETL-Worlds-Largest-Banks
developing an automated Python solution to extract, transform, and load (ETL) data on the top 10 largest banks in the world based on market capitalization.

#### Project Overview:
developing an automated Python solution to extract, transform, and load (ETL) data on the **top 10 largest banks in the world** based on market capitalization. The data needs to be transformed to include market capitalization in various currencies (GBP, EUR, INR) using exchange rate information provided in a separate CSV file. This system will be used to generate reports for the organization on a quarterly basis.

The final output will include:
- A **CSV file** containing the market capitalization of the top 10 banks in USD, GBP, EUR, and INR.
- A **database** storing the same information for easier querying and analysis.

The process must be fully automated so that the same script can be run every financial quarter to ensure up-to-date information is compiled.

### Project Details:

- **Code Name**: `banks_project.py`
- **Data Source URL**: [Top 10 Largest Banks by Market Capitalization](https://web.archive.org/web/20230908091635/https://en.wikipedia.org/wiki/List_of_largest_banks)
- **Exchange Rate CSV Path**: [Exchange Rate Data](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-PY0221EN-Coursera/labs/v2/exchange_rate.csv)
- **Initial Table Attributes (Upon Extraction)**: `Name`, `MC_USD_Billion`
- **Final Table Attributes (After Transformation)**: `Name`, `MC_USD_Billion`, `MC_GBP_Billion`, `MC_EUR_Billion`, `MC_INR_Billion`
- **Output CSV File Path**: `./Largest_banks_data.csv`
- **Database Name**: `Banks.db`
- **Database Table Name**: `Largest_banks`
- **Log File Name**: `code_log.txt`

### Project Tasks:

#### **Task 1: Log Progress**  
- **Objective**: Write a function `log_progress()` to track and log the progress of the script at different stages.
- **Details**: Use logging to create entries in `code_log.txt` at key points in the process, such as after extraction, transformation, loading to CSV, and loading to the database.

#### **Task 2: Data Extraction**  
- **Objective**: Extract the list of the top 10 largest banks by market capitalization from the provided URL.
- **Details**:
  1. Inspect the webpage to identify the position and structure of the table containing the required data.
  2. Write a function `extract()` to scrape the data and load it into a DataFrame.
  3. Execute the extraction and verify that the DataFrame correctly contains the list of banks with their market capitalization in USD.

#### **Task 3: Data Transformation**  
- **Objective**: Transform the extracted data by converting market capitalization from USD to GBP, EUR, and INR using the exchange rate data provided in the CSV file.
- **Details**:
  1. Write a function `transform()` that adds new columns for the market capitalization in GBP, EUR, and INR based on the provided exchange rates.
  2. Ensure that all values are rounded to two decimal places.
  3. Verify that the transformation correctly computes the market capitalization in all four currencies.

#### **Task 4: Load Data to CSV**  
- **Objective**: Save the transformed DataFrame to a CSV file.
- **Details**:
  - Write a function `load_to_csv()` to write the transformed data to `Largest_banks_data.csv`.
  - Verify that the output CSV file contains the correct data.

#### **Task 5: Load Data to SQL Database**  
- **Objective**: Load the transformed data into an SQLite database.
- **Details**:
  1. Write a function `load_to_db()` that creates a table in the database and inserts the transformed data.
  2. Ensure the table is created if it does not already exist and that the data is correctly inserted.
  3. Verify that the data is loaded into the `Largest_banks` table in the `Banks.db` database.

#### **Task 6: Query the Database**  
- **Objective**: Run SQL queries on the database to retrieve and verify the data.
- **Details**:
  1. Write a function `run_query()` to execute a SQL query that retrieves banks with market capitalization greater than 100 billion USD.
  2. Display the results of the query and ensure they are correct.

#### **Task 7: Verify Log Entries**  
- **Objective**: Verify that the `code_log.txt` file contains log entries for all the key stages.
- **Details**: After completing all tasks, check the log file to ensure that the process is fully logged, including the start and end of the ETL process, and the completion of each task.

### Expected Outcomes:
1. **CSV Output**: A file `Largest_banks_data.csv` containing the list of top 10 largest banks and their market capitalization in USD, GBP, EUR, and INR.
2. **Database Output**: An SQLite database file `Banks.db` with a table `Largest_banks` storing the same data.
3. **SQL Query Results**: A query output showing the banks with market capitalization greater than 100 billion USD.
4. **Log File**: A log file `code_log.txt` capturing the execution progress with timestamps at each stage.

### Tools and Technologies:
- **Python**: For implementing the ETL process.
- **Libraries**:
  - `requests` and `BeautifulSoup` for web scraping.
  - `pandas` for data manipulation and storage in CSV format.
  - `sqlite3` for interacting with the SQLite database.
  - `logging` for tracking progress and errors during the execution.
  
### Conclusion:
This project will automate the process of gathering, transforming, and storing data on the top 10 largest banks in the world by market capitalization, enabling the research organization to generate up-to-date reports every quarter. The code will fetch the latest data from the internet, apply necessary currency conversions, and store the data in both CSV and database formats for easy querying and analysis. The progress will be logged to ensure traceability and error handling during the process.

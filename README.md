# Designing-a-Bank-Marketing-DB
This Data Engineering project involves creating a comprehensive database to store and manage customer information for a bank's marketing campaigns.

# Project Description
### Problem Statement

You have been asked to work with a bank to clean and store the data they collected as part of a recent marketing campaign, which aimed to get customers to take out a personal loan. They plan to conduct more marketing campaigns going forward so would like you to set up a PostgreSQL database to store this campaign's data, designing the schema in a way that would allow data from future campaigns to be easily imported.

They have supplied you with a csv file called "bank_marketing.csv", which you will need to clean, reformat, and split, in order to save separate files based on the tables you will create. It is recommended to use pandas for these tasks.

Lastly, you will write the SQL code that the bank can execute to create the tables and populate with the data from the csv files. As the bank are quite strict about their security, you'll save SQL files as multiline string variables that they can then use to create the database on their end.

You have been asked to design a database that will have three tables:

## client
| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `id` | `serial` | Client ID - primary key | `client_id` |
| `age` | `integer` | Client's age in years | `age` |
| `job` | `text` | Client's type of job | `job` |
| `marital` | `text` | Client's marital status | `marital` | 
| `education` | `text` | Client's level of education | `education` |
| `credit_default` | `boolean` | Whether the client's credit is in default | `credit_default` |
| `housing` | `boolean` | Whether the client has an existing housing loan (mortgage) | `housing` | 
| `loan` | `boolean` | Whether the client has an existing personal loan | `loan` |

## campaign

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `campaign_id` | `serial` | Campaign ID - primary key | N/A - new column |
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `number_contacts` | `integer` | Number of contact attempts to the client in the current campaign | `campaign` |
| `contact_duration` | `integer` | Last contact duration in seconds | `duration` |
| `pdays` | `integer` | Number of days since contact in previous campaign (`999` = not previously contacted) | `pdays` |
| `previous_campaign_contacts` | `integer` | Number of contact attempts to the client in the previous campaign | `previous` |
| `previous_outcome` | `boolean` | Outcome of the previous campaign | `poutcome` |
| `campaign_outcome` | `boolean` | Outcome of the current campaign | `y` |
| `last_contact_date` | `date` | Last date the client was contacted | A combination of `day`, `month`, and the newly created `year` |

## economics

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `emp_var_rate` | `float` | Employment variation rate (quarterly indicator) | `emp_var_rate` |
| `cons_price_idx` | `float` | Consumer price index (monthly indicator) | `cons_price_idx` |
| `euribor_three_months` | `float` | Euro Interbank Offered Rate (euribor) three month rate (daily indicator) | `euribor3m` |
| `number_employed` | `float` | Number of employees (quarterly indicator)| `nr_employed` |


# Project Tasks

View the notebook (Bank_Marketing_DB.ipynb) to see the project tasks and all expected output for each task.

successfully load the data into a PostgreSQL database after cleaning and getting it ready.

![camp](https://github.com/Abhi707-bot/Designing-a-Bank-Marketing-DB/assets/68341067/1d364da1-24e5-4b7c-8f0a-9c5aca640fbd)

![cli](https://github.com/Abhi707-bot/Designing-a-Bank-Marketing-DB/assets/68341067/17d6a427-2bfb-4210-9d69-53e4d94eaeb0)

![eco](https://github.com/Abhi707-bot/Designing-a-Bank-Marketing-DB/assets/68341067/dd91222e-7a4f-4236-8603-c7e010494303)



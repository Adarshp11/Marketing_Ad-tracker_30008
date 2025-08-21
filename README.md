# Marketing_Ad-tracker_30008

# Digital Ad Campaign Tracker 📊

This is a Streamlit-based web application that serves as a digital ad campaign tracker. It allows you to perform **C**reate, **R**ead, **U**pdate, and **D**elete (**CRUD**) operations on ad campaign data stored in a PostgreSQL database.

## Features ✨

  * **Dashboard View:** A clean dashboard displays key performance indicators (KPIs) like total cost, average clicks, and derived metrics such as Cost Per Click (CPC) and Conversion Rate (CVR).
  * **Data Management:** Easily add, edit, or delete campaign records directly from the user interface.
  * **Data Filtering & Sorting:** Filter campaigns by platform (e.g., Google Ads, Facebook Ads) and sort them by cost, clicks, or conversions to gain quick insights.
  * **Robust Backend:** The application is powered by a PostgreSQL database for reliable data storage and a Python backend for efficient data operations.

-----

## Prerequisites 🛠️

Before running the application, ensure you have the following installed:

  * **Python 3.8+**
  * **PostgreSQL** (with the database `Ad_tracker` created)

## Setup and Installation 🚀

### 1\. Database Setup

First, you need to create the `Ad_tracker` database and the `campaigns` table.

Open your PostgreSQL command-line tool or a GUI like pgAdmin and run the following SQL command:

```sql
CREATE DATABASE "Ad_tracker";
```

Next, connect to the `Ad_tracker` database and create the `campaigns` table using the provided `sql_schema.sql` file.

```sql
CREATE TABLE IF NOT EXISTS campaigns (
    campaign_id VARCHAR(255) PRIMARY KEY,
    campaign_name VARCHAR(255) NOT NULL,
    platform VARCHAR(50),
    start_date DATE,
    cost DECIMAL(10, 2),
    clicks INTEGER,
    conversions INTEGER
);
```

### 2\. Install Python Dependencies

Navigate to your project directory and install the required Python libraries using pip:

```bash
pip install -r requirements.txt
```

If you do not have a `requirements.txt` file, you can create one with the following contents and then run the command above:

```
streamlit
psycopg2-binary
pandas
```

### 3\. Configure Database Connection

The application uses hard-coded credentials for simplicity. You can find and modify them in the `database.py` file to match your PostgreSQL setup.

```python
# database.py
DB_HOST = "localhost"
DB_NAME = "Ad_tracker"
DB_USER = "postgres"
DB_PASSWORD = "1155"
DB_PORT = "5433"
```

### 4\. Run the Application

Once everything is set up, run the Streamlit application from your terminal:

```bash
streamlit run Ad_tracker.py
```

This command will open the application in your web browser. The first time you run it, the `database.py` script will automatically seed some sample data to get you started.

-----

## File Structure 📂

  * `Ad_tracker.py`: The frontend application built with Streamlit, handling the user interface and interactions.
  * `database.py`: The backend Python file that contains all database-related functions for CRUD operations and data aggregation.
  * `sql_schema.sql`: A simple SQL script for creating the necessary database table.
  * `requirements.txt`: A list of all Python dependencies required to run the project.

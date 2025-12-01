# n8n-email-to-postgres-automation
Automated Gmail → CSV → Postgres mini project using n8n

# n8n: Automated Gmail → CSV → Postgres Pipeline

This mini-project automates the process of receiving monthly CSV reports by email and inserting them directly into a Postgres database using **n8n**.  
It eliminates all manual CSV imports and keeps your data up-to-date automatically.

---

## 🚀 Project Overview

Whenever someone sends a CSV file to your Gmail inbox:

1. **Gmail Trigger** activates on new mail  
2. **Get Message** pulls the email + attachment(s)  
3. **Extract From File** parses the CSV into structured JSON rows  
4. **Insert Rows in Table** writes the data into a Postgres table  

The entire workflow is event-driven and runs without human involvement.

---

## 🧩 Workflow Screenshots

All workflow screenshots are located in:

screenshots/

yaml
Copy code

---

## 📂 Project Structure

.
├── infra/
│ └── schema.sql # Postgres table schema
├── workflow/
│ └── n8n-workflow-email-to-postgres.json # Exported n8n automation
├── sample_month.csv # Sample input CSV
├── screenshots.zip # Workflow screenshots
├── LICENSE
└── README.md

yaml
Copy code

---

## 🗄️ Database Schema

Located in:

infra/schema.sql

pgsql
Copy code

Example (update as per your CSV):

```sql
CREATE TABLE monthly_sales (
    order_id        INTEGER,
    customer_id     INTEGER,
    order_date      DATE,
    amount          NUMERIC(10,2),
    product         TEXT
);
📝 Sample CSV
A test CSV file is included:

Copy code
sample_month.csv
Email it to yourself to verify the workflow end-to-end.

🔧 How to Run This Project Yourself
1. Install or open n8n
Use one of these options:

n8n.cloud (recommended)

Local Docker installation

Local desktop install

2. Import the workflow into n8n
pgsql
Copy code
Workflows → Import → Select JSON file
Select:

pgsql
Copy code
workflow/n8n-workflow-email-to-postgres.json
3. Create credentials inside n8n
You need:

✔ Gmail OAuth

✔ Postgres DB credential

4. Update node configuration
Open each node and connect the appropriate credential:

Gmail Trigger

Get Message

Extract from File

Insert Rows in Table

5. Test the workflow
Email yourself the sample_month.csv file

Execute the workflow manually

Check your Postgres table for new rows

🎯 Why This Project Matters
This project demonstrates your ability to:

Build end-to-end automation pipelines

Integrate email, file parsing, and databases

Use n8n for low-code workflow automation

Handle structured CSV ingestion

Solve real-world data engineering problems for analysts/DA roles

This is exactly the type of practical automation that companies love.

📄 License
MIT License

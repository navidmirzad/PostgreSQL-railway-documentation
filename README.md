![image](https://github.com/user-attachments/assets/041bf224-7b1c-408b-b9df-95184c692515)# PostgreSQL-railway-documentation
RLS - Railway.app

📖 Documentation for Integrating with PostgreSQL Database
Introduction
For this project, my initial thought was to use MySQL since I had the most experience with it. However, after evaluating various databases, I decided to use PostgreSQL due to its fine-grained access control and robust security at both row and column levels (db-engines.com, 2025).

Why PostgreSQL?
<br>
✅ Supports strict security down to the row and column level
✅ Allows granular access control using roles and privileges
✅ Supports custom objects, inheritance, and polymorphism (object-relational DB)
✅ Well-suited for structured data and complex queries

🔴 Downside: Unlike MongoDB, which supports a wide variety of programming languages, PostgreSQL primarily focuses on popular and widely-used languages.

2. Getting Started with PostgreSQL
📌 Installation
# Windows
Download PostgreSQL from the official site: https://www.postgresql.org/download/

Alternative (via Chocolatey)
Open PowerShell as Administrator and run:
- choco install PostgreSQL

Important: If you select A (for installing scripts), an auto-generated password will be set. Copy it for later use.

PostgreSQL by default runs on port: 5432

# macOS

Install PostgreSQL via Homebrew:
- brew install PostgreSQL

Start PostgreSQL service:
- brew services start progresql

Access PostgreSQL using:
- psql postgres

3. Connecting to the Database
📌 Default Connection
Once PostgreSQL is installed, open PowerShell (Windows) or Terminal (macOS) and connect to the default postgres database:
- psql -U postgres
(If prompted, enter the password set during installation.)

4. Connecting to the Hosted Railway PostgreSQL Database
💻 Connection Command (Windows/macOS)
To connect to the Railway-hosted PostgreSQL database, use the following commands depending on the role:

I have three different users in my database:
- admin with the password "admin"
- read_only_dept, password "readonly"
- emp1, password emp1

# for Windows

- $env:PGPASSWORD="password-for-given-user" psql -h shinkansen.proxy.rlwy.net -U admin -p 10363 -d railway

# for macOS:

- PGPASSWORD="password-for-given-user" psql -h shinkansen.proxy.rlwy.net -U admin -p 10363 -d railway

6. Database Roles & Permissions
Database has the following roles (users):

![image](https://github.com/user-attachments/assets/d9d407c7-27ef-4d76-a477-e5a218c7b0ee)

5. PostgreSQL Basic Commands
📌 List all databases

- \l

📌 Connect to a specific database

- \c database_name

📌 List all tables in the current database

- \dt

📌 List all roles (users) in the database

- \du

📌 Show table schema

\d table_name


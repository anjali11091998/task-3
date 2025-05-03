# Task -3






MySQL to PostgreSQL Migration with DBeaver (GUI Method) DBeaver is a free, open-source, cross-platform database management tool that supports both MySQL and PostgreSQL. It offers a Data Transfer Wizard that simplifies database migration without writing much code.

## Step-by-Step Migration Using DBeaver

✅**1. Install DBeaver**

Download from https://dbeaver.io/download/

Install and launch the application.

✅**2. Connect to Your MySQL Database**

Click Database > New Database Connection.

Choose MySQL, then:

Enter host, port (default: 3306), username, and password.

Test connection and finish.

✅**3. Connect to Your PostgreSQL Database**

Same steps as above, but choose PostgreSQL.

Default port is 5432.

Create the target database manually first using DBeaver or psql if needed.

✅**4. Open Data Transfer Wizard**

Right-click the MySQL database or table(s) you want to migrate.

Select Tools > Data Transfer.

✅**5. Configure the Data Transfer**

Source: Your selected MySQL tables.

Target: Select PostgreSQL connection and the destination schema.

Choose:

Transfer type: Data Only, DDL Only, or both.

Mapping: DBeaver will attempt automatic type mapping, but you can manually override (e.g., map TINYINT(1) → BOOLEAN).

✅**6. Advanced Settings (Optional)**

You can configure:

Truncate existing tables.

Skip constraints or indexes for faster import.

Batch size and commit frequency.

Enable error logging if needed.

✅**7. Execute the Migration**

Click Start to begin the migration.

DBeaver shows a progress bar and logs.

After completion, verify in the target PostgreSQL DB.

✅**8. Post-Migration Validation**


Run queries in PostgreSQL to confirm:

sql

Copy

Edit

SELECT COUNT(*) FROM migrated_table;

Compare results with MySQL to verify data integrity.

Manually migrate any stored procedures, triggers, or views.

**Notes & Tips** 

DBeaver does not migrate stored procedures/functions automatically.

You may need to manually adjust schema if there are incompatible types.

It's ideal for small to medium projects, not high-volume real-time data replication.

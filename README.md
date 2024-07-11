# Cloud Integration Mentoring: Deploying PostgreSQL in Microsoft Azure

## Project Description
You've recently joined a traditional on-premises team as a Cloud Specialist. The primary task is to bridge the gap between on-premises knowledge and cloud technologies by mentoring the team. The team, with years of experience in on-premises environments, is new to the concept of cloud. Your mission is to guide them through the process of deploying a PostgreSQL database on Microsoft Azure. This involves demonstrating the creation and connection of the database service, setting up a new schema and table, and executing queries.

## Steps

1. **Azure Database for PostgreSQL servers**
   - **Server name**: jwdatabase01
   - **Configure server**:
     - Burstable tier
     - Storage size: 32GB
     - Performance tier: P4
     - Give Admin username and Password
     - Add firewall rule: All public access allowed, or select public IP
       - This can be accessed later under 'Settings > Networking'

2. **Download pgAdmin (Must use v4-8.9)**
   - Create password
   - In pgAdmin, navigate to Servers > Register > Server
     - **General**: Copy `Server name` from Azure, paste in pgAdmin
     - **Connection**:
       - Host name/address: Same server name, default Port
       - Username: Copy 'Server admin login name' from Azure (e.g., sql)
       - Password: Save password
  
![https://i.imgur.com/6UifWb8.png](https://i.imgur.com/6UifWb8.png)![https://i.imgur.com/oKeUWub.png](https://i.imgur.com/oKeUWub.png)

3. **Database and Schema Creation in pgAdmin**
   - In pgAdmin, expand Database, right click and create new database
     - **General [tab]**: Name it db01, then Save
    
![https://i.imgur.com/QrXxyFT.png](https://i.imgur.com/QrXxyFT.png)

   - Right click Schema, name it app01 (Databases > Schemas)
   - Create new Table, name it employees (Databases > Schemas > app01 > Tables)
     - Columns:
       - Name: id, Data type: integer
       - Name: name, Data type: character, Length/precision: 200
      
![https://i.imgur.com/tDnesmt.png](https://i.imgur.com/tDnesmt.png)

4. **Executing Queries**
   - Click Query Tool next to Object Explorer (if there, click on icon)
   - Run the following commands to add Bob Smith to the table, and check the table:
     ```sql
     INSERT INTO app01.employees VALUES (1, 'Bob Smith');
     SELECT * FROM app01.employees;
     ```
![https://i.imgur.com/4pWOxQ7.png](https://i.imgur.com/4pWOxQ7.png)

## What I Learned
During this project, I gained valuable insights into the process of deploying and managing PostgreSQL databases in the Microsoft Azure environment. Some key takeaways include:

- Understanding the configuration options and tiers available for Azure Database for PostgreSQL.
- The importance of setting up proper firewall rules to manage access to the database.
- How to use pgAdmin to manage and interact with PostgreSQL databases effectively.
- The steps involved in creating databases, schemas, tables, and running queries in PostgreSQL.
- The practical experience of bridging the knowledge gap between on-premises and cloud environments for a team new to cloud technologies.

This project has enhanced my skills in cloud database management and provided me with the confidence to mentor others in similar transitions.

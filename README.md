## Overview
The purpose of this is to demonstrate what happens when a voter database, including web forms, are not developed well and have vulnerabilities.

## Audience
1. Govies, lawmakers, politicians
2. Developers

## DISCLAIMER
* Because this is a deliberately vulnerable system, DO NOT launch this on the real Internet!
* Please DO NOT attack your state's actual "Find my voter registration status" page.

## Requirements
* Web server (e.g., nginx)
* MySQL / MariaDB
* PHP (latest)
  - `php-mysql` extension enabled

## Database Setup Instructions
1. Create database in MySQL: `CREATE DATABASE voterdb;`

2. Create database table in the `voterdb` database:
`CREATE TABLE voters (`
`id INT(9) NOT NULL AUTO_INCREMENT,`
`first_name VARCHAR(30) NOT NULL,`
`last_name TEXT NOT NULL,`
`dob_month INT(2) NOT NULL,`
`dob_day INT(2) NOT NULL,`
`dob_year INT(4) NOT NULL,`
`zipcode VARCHAR(5) NOT NULL DEFAULT '00000',`
`PRIMARY KEY(id));`

3. Insert the seed data to the database.  The seed data file is found in the `data` folder
  - Example: `sudo mysql voterdb < insert_fake_voter_data.sql`

## Additional Support
In the `data` folder, there is a Python script to generate fake voter data.

## References
1. https://us-cert.cisa.gov/ncas/tips/ST16-001
2. "SQL Injection Attack is Tied to Election Commission Breach" https://threatpost.com/sql-injection-attack-is-tied-to-election-commission-breach/122571/
3. "How the Russians penetrated Illinois election computers" https://abc7chicago.com/politics/how-the-russians-penetrated-illinois-election-computers/3778816/
4. "US Alleges Iran Sent Threatening Emails to Democrats" https://www.bankinfosecurity.com/us-alleges-iran-sent-threatening-emails-to-democrats-a-15221
5. "Free tech tools for election officials" https://gcn.com/articles/2020/10/08/election-security-tools.aspx
6. "U.S. Voter Databases Offered for Free on Dark Web, Report" https://threatpost.com/u-s-voter-databases-offered-free-dark-web/158840/

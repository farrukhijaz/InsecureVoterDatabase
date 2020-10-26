## Overview
The purpose of this is to demonstrate what happens when a voter database, including web forms, are not developed well and have vulnerabilities.

## Design
This page is actually a copy of the actual "Find my voter registration status" page at https://www.sec.state.ma.us/voterregistrationsearch/myvoterregstatus.aspx. However, this system is deliberately vulnerable.  An attacker can dump the entire contents of this database.

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
In the `data` folder, there is a Python script to generate fake voter data
# SQL Injection Lab

## Overview
This project demonstrates the exploitation and mitigation of SQL injection vulnerabilities in a web application. The lab was conducted in a Docker-based environment simulating a real-world client-server architecture with a backend MySQL database.

## Environment
- Docker & Docker Compose
- Vulnerable web application
- MySQL database
- SEED Labs environment

## Vulnerability Analysis
The application constructs SQL queries by directly embedding user input into query strings without sanitization. This allows attackers to manipulate query logic and execute unintended operations.

## Exploitation

### Authentication Bypass
By injecting a crafted payload (`admin' OR '1'='1`), authentication checks were bypassed, allowing unauthorized access to administrative accounts.

### Data Extraction
SQL queries were manipulated to retrieve sensitive user data from the backend database, demonstrating the lack of access control.

### Unauthorized Data Modification
Injection into UPDATE statements enabled modification of database records, including altering user credentials and financial data.

## Impact
- Full authentication bypass
- Unauthorized data access
- Privilege escalation
- Data integrity compromise

## Mitigation
The vulnerability was resolved using **prepared statements**, ensuring that user input is treated strictly as data rather than executable SQL.

## Key Takeaways
- Importance of input validation
- Risks of dynamic SQL query construction
- Effectiveness of parameterized queries
